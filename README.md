# Ottley · SMART on FHIR launch build

Static files only. Host this folder on any HTTPS site; there's no server and no build step.

- `launch.html` is the SMART launch URL. The EHR or the launcher opens it with `?iss=...&launch=...`.
- `index.html` is Ottley. After authorization it reads Patient, MedicationRequest, MedicationStatement, AllergyIntolerance and weight/height Observations, then maps them into a draft.
- `fhir-client.min.js` is the SMART client library (fhirclient 2.5.4, Apache-2.0), vendored so no CDN is needed.

The app is read-only: it doesn't write back to the EHR. Use synthetic or sandbox patients only.

## Try it in the SMART launcher
1. Open https://launch.smarthealthit.org
2. Set Launch Type to "Provider EHR Launch" and FHIR Version to R4.
3. Pick a patient and a provider, or leave them blank and the launcher asks you to choose.
4. Turn on "Simulate launch within the EHR UI" to see Ottley inside a mock EHR frame.
5. App Launch URL: `https://<your-host>/launch.html`
6. Click Launch.

The client ID can be anything in the launcher. The app uses `ottley-demo`, or whatever `?client_id=` you add to launch.html.
