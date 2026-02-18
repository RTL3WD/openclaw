# MiniMax OAuth (OpenClaw plugin)

OAuth provider plugin for **MiniMax** (OAuth).

## Enable

Bundled plugins are disabled by default. Enable this one:

```bash
openclaw plugins enable minimax-portal-auth
```

Restart the Gateway after enabling.

```bash
openclaw gateway restart
```

## Authenticate

```bash
openclaw models auth login --provider minimax-portal --set-default
```

You will be prompted to select an endpoint:

- **Global** - International users, optimized for overseas access (`api.minimax.io`)
- **China** - Optimized for users in China (`api.minimaxi.com`)

## Environment Variables (Optional)

Override default OAuth client IDs with environment variables:

- `OPENCLAW_MINIMAX_OAUTH_CLIENT_ID_CN` / `MINIMAX_OAUTH_CLIENT_ID_CN` - Client ID for China region
- `OPENCLAW_MINIMAX_OAUTH_CLIENT_ID_GLOBAL` / `MINIMAX_OAUTH_CLIENT_ID_GLOBAL` - Client ID for Global region

**Security Best Practice**: When using custom OAuth applications, set these environment variables instead of hardcoding credentials in code.

Example:

```bash
export OPENCLAW_MINIMAX_OAUTH_CLIENT_ID_GLOBAL="your-custom-client-id"
openclaw models auth login --provider minimax-portal --set-default
```

## Notes

- MiniMax OAuth uses a user-code login flow.
- Currently, OAuth login is supported only for the Coding plan
- Default client IDs are provided as fallback when environment variables are not set
