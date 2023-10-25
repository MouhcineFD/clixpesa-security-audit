# clixpesa-security-audit
Security report for https://github.com/clixpesa/clixpesa-mvp/tree/main/packages/dapp 25/10/2023

## Issue: Outdated Package Dependencies

- **Description:** The project contains high-severity vulnerabilities due to outdated package dependencies.
- **Likelihood:** 1/5
- **Impact:** 5/5
- **Recommendation:** Update the project's package dependencies to their latest versions based on the result of Yarn audit. Utilize the resolution attribute in the package.json file to force installing fixed versions.

## Issue: Public Code Exposure

- **Description:** The project code is public and accessible to anyone.
- **Likelihood:** 5/5
- **Impact (If it will be private):** 5/5
- **Impact (If it will stay public):** 0/5
- **Recommendation:** Ensure that any private keys or sensitive information are not stored in the public repository. Turn it private now if it will be the case in the future.

## Issue: No Screen Capture Protection

- **Description:** Screens in the app are not protected from capture or recording, risking exposure of sensitive data.
- **Likelihood:** 4/5
- **Impact:** 4/5
- **Recommendation:** Implement a screen capture protection mechanism like "expo-screen-capture" to safeguard sensitive data from being captured or recorded.

## Issue: Error Exception Handling

- **Description:** Some error exceptions may leak sensitive data in error reporting/monitoring.
- **Likelihood:** 2/5
- **Impact:** 4/5
- **Recommendation:** Carefully review all error handling and ensure that no sensitive data is exposed in error reports. Pay special attention to the areas mentioned in the recommendations.
   - See `blockchain/provider.js` line 42
   - See `utils/addresses.js`

## Issue: Lack of Rooted/Jailbroken Device Protection

- **Description:** The app does not protect against rooted/jailbroken devices, potentially exposing sensitive information.
- **Likelihood:** 2/5
- **Impact:** 4/5
- **Recommendation:** Implement device checks to make the app unusable on rooted or jailbroken devices, enhancing security against physical attacks.

## Issue: Lack of Obfuscation

- **Description:** No code obfuscation is implemented, potentially exposing sensitive information.
- **Likelihood:** 4/5
- **Impact (If it will be private):** 3/5
- **Impact (If it will stay public):** 0/5
- **Recommendation:** Enable code obfuscation, especially if the project is intended to become private, to protect sensitive information.

## Issue: Excessive Console Logging

- **Description:** Excessive console logs may potentially leak sensitive data.
- **Likelihood:** 2/5
- **Impact:** 3/5
- **Recommendation:** Review and remove unnecessary console logs in the codebase, such as those mentioned in the recommendations.
   - See `/features/essentials/onboarding/set-passcode.screen.jsx` line 21
   - See `/features/spaces/spaces-home.screen.jsx` line 34 and 107
   - See `/features/wallet/pending-wallet.js` line 19

## Issue: External Image Usage

- **Description:** The project uses images from external resources, potentially risking unavailability or containing unwanted content.
- **Likelihood:** 3/5
- **Impact:** 2/5
- **Recommendation:** Use local images or ensure proper ownership and permissions for external resources to avoid potential risks.
   - See `features/spaces/customize-p.screen.jsx` line 24
   - See `features/spaces/customize-personal.screen.jsx` line 17
   - See `features/spaces/create-space.screen.jsx` line 25

## Issue: Persistent Wallet and User Info on device storage

- **Description:** Without uninstalling the app from the device, the wallet and user information remain in secure storage.
- **Likelihood:** 1/5
- **Impact:** 1/5
- **Recommendation:** Implement a mechanism to securely clean wallet and user information from the secure storage upon user logout, enhancing data protection.

## Issue: Useless Phone Number Verification Step

- **Description:** The phone number verification step is automatically bypassed.
- **Likelihood:** 5/5
- **Impact:** 1/5
- **Recommendation:** Implement a real phone number verification method to enhance security and prevent bypasses.


Please address these issues to enhance the security and privacy of your project. Consider the recommendations to mitigate the potential risks and protect sensitive information.
