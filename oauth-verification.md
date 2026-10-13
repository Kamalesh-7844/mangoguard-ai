# OAuth Redirect Verification

Verified on 2026-09-09 in the live MangoGuard AI preview.

The sign-in action opened the Manus provider with this redirect URI:

`https://3000-if6krdhdk5i8k4lirgynu-fdc5ef62.sg2.manus.computer/api/oauth/callback`

The provider loaded the normal “Sign in to MangoGuard AI” screen and did not display the previous `invalid redirect_uri` error. The URI is derived from `window.location.origin` in `client/src/const.ts`. Local browser sessions opened on `127.0.0.1` are redirected to the equivalent `localhost` origin before OAuth state and cookies are created.

End-to-end account completion was not performed because it requires user account interaction; the provider acceptance and redirect URI generation were verified successfully.
