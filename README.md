# Copilot Studio SSO (GitHub Pages)

Static GitHub Pages site that hosts a Bot Framework Web Chat client wired to a Microsoft Copilot Studio agent using Entra ID SSO.

It includes an automatic sign-in experience:

- First tries **silent SSO** (`ssoSilent`) on page load
- If silent SSO is not possible, falls back to **redirect login** (`loginRedirect`) for a no-click login flow

## Project Structure

- **docs/index.html**: The Web Chat + MSAL (SSO) sample page (this is what GitHub Pages serves)
- **docs/assets/styles.css**: Optional styling
- **docs/sso/index.md**: SSO notes
- **docs/sso/troubleshooting.md**: Troubleshooting notes

## Live Site

Once GitHub Pages is enabled for this repo, the site is available at:

- `https://sujieshd.github.io/copilot-studio-sso-gh-pages/`

## Configure Entra ID (App Registration)

Create/register an app in Entra ID and configure it for a browser-based SPA flow.

1. **Authentication → Platform configurations**
	 - Add a platform: **Single-page application (SPA)**
	 - Add Redirect URI:
		 - `https://sujieshd.github.io/copilot-studio-sso-gh-pages/`
2. **API permissions**
	 - Add permissions needed for your login scenario (the sample uses `openid`, `profile`, and `User.Read`)

Notes:

- Silent SSO may fail in some browsers due to tracking prevention / third-party cookie restrictions.
- The page falls back to `loginRedirect()` to avoid popup blocking and remove the need for a manual click.

## Configure Copilot Studio SSO

Follow the Copilot Studio SSO configuration steps and ensure your bot channel is set up for token exchange.

Reference:

- https://learn.microsoft.com/en-us/microsoft-copilot-studio/configure-sso

## Configure This Repo

Edit these constants in `docs/index.html`:

- `clientId`: Entra ID app (client) ID
- `tenantId`: Entra tenant ID
- `tokenEndpoint`: Copilot Studio Direct Line token endpoint

## Local Development

1. Clone the repository to your local machine.
2. Navigate to the project directory.

Option A (quickest):

- Use any static file server and browse to `/docs/index.html`.
	- Example: VS Code Live Server extension

Option B (Jekyll):

- `bundle install`
- `bundle exec jekyll serve`
- Open `http://localhost:4000/`

## Troubleshooting

- If you see the bot asking you to log in, check browser console logs and verify your Entra Redirect URI matches exactly.
- If silent SSO fails, it’s often expected; redirect login is the designed fallback.

## Contributing

Contributions are welcome! Please submit a pull request or open an issue for any enhancements or bug fixes.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.