# translator
This is a simple language translator web application designed using HTML,Vanilla Javascript and CSS.The actual translation is performed by an external API, and the code provides a user-friendly interface for interacting with the translation service.
It contains the following functionality:

1. **Element Selection:**
   - It selects various DOM elements using `document.querySelector` and `document.querySelectorAll`. These elements include the source and target text areas, the exchange icon, language selection dropdowns, icons, and the translate button.

2. **Populating Language Dropdowns:**
   - It populates the language selection dropdowns with options. It iterates through a `countries` object to generate options for both source and target languages. The selected language is marked as "selected" in each dropdown.

3. **Exchange Icon Click Event:**
   - When the exchange icon is clicked, it swaps the values between the source and target text areas and also exchanges the selected options in the language selection dropdowns. This allows users to quickly switch the translation direction.

4. **Keyup Event on fromText:**
   - It adds a `keyup` event listener to the source text area. If the source text area is empty, it clears the target text area. This provides real-time feedback to the user as they type.

5. **Translate Button Click Event:**
   - When the "Translate Text" button is clicked, the code performs the following steps:
     - Retrieves the text to be translated, the source language, and the target language.
     - Sets a "Translating..." placeholder in the target text area.
     - Constructs an API URL to request the translation, using an external translation API (https://api.mymemory.translated.net).
     - Fetches the translation data, processes it, and updates the target text area with the translated text. It also replaces the "Translating..." placeholder with "Translation."

6. **Icon Click Events:**
   - It adds click event listeners to various icons. These icons have two functions:
     - If the "copy" icon is clicked, it uses the Clipboard API to copy the content of either the source or target text area to the clipboard.
     - If the "volume" (speaker) icon is clicked, it uses the Web Speech API to speak the text from either the source or target text area, based on the selected language.

