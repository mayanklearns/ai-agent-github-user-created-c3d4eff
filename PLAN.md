### Architectural Vision
The existing file structure (`index.html`, `script.js`, `styles.css`) will be maintained.
- `index.html`: Will be modified to include the `username-count` element and a warning message element near the username input field.
- `script.js`: Will be updated to include an event listener for the username input, logic for counting characters, updating the `username-count` element, and displaying/hiding the warning message.
- `styles.css`: Will be updated to include styles for the warning message.

### Component Strategy
- **`index.html` modifications**:
    - Locate the `div` containing the `username` input field.
    - Inside this `div`, after the `input` element, add a `small` element with `id="username-count"` to display the character count.
    - After the `username-count` element, add another `small` element with `id="username-warning"` to display the warning message when the character limit is exceeded. This element will initially be hidden.

### Styling Strategy
- **`styles.css` modifications**:
    - Add a CSS class (e.g., `.text-danger`) for the warning message to make it red. Bootstrap already has `text-danger`, so I'll use that.
    - Ensure the warning message is hidden by default using `d-none` from Bootstrap.

### Logic & Interactivity
- **`script.js` modifications**:
    1.  **Get DOM Elements**:
        - Get references to the `username` input field (`#username`).
        - Get references to the `username-count` element (`#username-count`).
        - Get references to the `username-warning` element (`#username-warning`).
    2.  **Event Listener**:
        - Add an `input` event listener to the `username` input field.
    3.  **Character Counting Logic**:
        - Inside the event listener, get the current value of the `username` input.
        - Update the `textContent` of `username-count` with the current character length.
    4.  **Warning Display Logic**:
        - If the character length exceeds 39:
            - Display the `username-warning` element (remove `d-none`).
            - Add a class to `username-count` to make it red (e.g., `text-danger`).
        - Otherwise:
            - Hide the `username-warning` element (add `d-none`).
            - Remove the red class from `username-count`.
    5.  **Initial State**:
        - On page load, initialize the character count and warning based on the initial (empty) input.

### Evaluation Criteria Compliance
-   **There is an element with ID 'username-count' that updates in real-time as the user types.**
    -   `index.html` will have `<small id="username-count"></small>`.
    -   `script.js` will have an `input` event listener on the username field that updates `username-count.textContent`.
-   **A warning is displayed if the username exceeds 39 characters.**
    -   `index.html` will have `<small id="username-warning" class="text-danger d-none">Username exceeds 39 characters!</small>`.
    -   `script.js` will check `username.value.length > 39` and toggle the `d-none` class on `username-warning`.
-   **The page still contains a script referencing 'username-count'.**
    -   The `script.js` will contain the logic for `username-count`.
-   **Existing functionality remains intact.**
    -   The changes will be isolated to the character counter and warning, not interfering with the existing GitHub API fetch logic.
-   **`README.md` is updated to reflect any new features and uses the provided URLs.**
    -   After implementing the code, I will update `README.md` with a new feature description and the provided URLs.