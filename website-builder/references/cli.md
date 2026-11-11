# DoAny CLI

The CLI needs Node.js 20 or later. Use `doany` if installed, or prefix each command with `npx -y @doany-ai/cli` in place of `doany`.

## Connect

Run `doany whoami` to check the connection, companies and scopes. On the user's computer, use `doany login` if they are signed out. The user completes consent in the browser. Ask only for the scopes the work needs. For example, to edit an existing site:

```bash
doany login --scopes 'projects:read apps:read annie:read annie:write'
```

Add `projects:create` if creating a company and `apps:publish` if publishing. On a remote machine or in CI where browser sign-in cannot return, have the user set `DOANY_API_KEY` in the environment where the command runs. They can create a scoped key in [DoAny API & MCP](https://doany.ai/company/api/keys). Use a key with **Skip confirmations** off. The user keeps the key in that environment.

For an explicitly requested test environment, set `DOANY_API_URL` to that environment's official API origin, use credentials for that environment, and set a separate `DOANY_CONFIG_DIR` for its CLI state. Check the connection before creating a project or task.

## Run a first build

Read `doany describe <operation-id>` before first use to confirm its flags, permissions, and next steps. Use explicit project and app IDs to keep commands on the intended website.

This example applies to a new, regular company. Set `PROJECT_ID` and `TASK_ID` to UUIDs you generate once and retain for retries. Set `NAME`, `IDEA`, and `BRIEF` to the agreed inputs. Obtain the user's go-ahead for the build before running the task command.

```bash
doany projects create --project-id "$PROJECT_ID" --name "$NAME" --idea "$IDEA"
doany tasks create --project-id "$PROJECT_ID" --task-id "$TASK_ID" \
  --message "$BRIEF" --require-publish-approval --wait --timeout 900
```

For an existing company, apply the site and policy checks in the main skill. Omit `--require-publish-approval` for the OAuth Default company or any already built site. For a longer brief, `--message-file` takes a file containing the user's instructions.

The CLI writes receipts as JSON to stdout and progress, confirmation previews and next steps to stderr. With `--wait`, exit `3` means approval is required, `4` means Annie has a question, `5` means the user must act in DoAny, and `6` means the wait ended while the task continues. Leave any interactive approval prompt to the user. In a noninteractive session, show the preview without the token, then replay the same action with the emitted `--confirmation-token` only after approval. For a question, use the current `--question-id` and the user's `--answer` values. To resume after a timeout, use:

```bash
doany tasks wait --project-id "$PROJECT_ID" --task-id "$TASK_ID"
```

## Publish a reviewed version

Read `doany apps get --project-id "$PROJECT_ID" --app-id "$APP_ID"` for the draft. Use `doany versions list --project-id "$PROJECT_ID" --app-id "$APP_ID"` to get the permanent URL for its checkpoint. Once the user has reviewed it, recheck the draft and pass both reviewed values to publish:

```bash
doany publish --project-id "$PROJECT_ID" --app-id "$APP_ID" \
  --checkpoint-id "$CHECKPOINT_ID" --source-commit "$SOURCE_COMMIT"
```

The CLI shows the publishing preview. Use the same pinned arguments with the confirmation token only after the user approves it. The CLI's [command guide](https://docs.doany.ai/api-mcp/cli) has the full exit-code and answer syntax.
