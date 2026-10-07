## PS 1: Online Course Registration Form

**Background**
A small coding academy wants a registration page for its upcoming batch. Before any design work starts, they need a working, accessible HTML structure that collects all the required student details.

**Objective**
Build a single-page registration form using only HTML (no CSS, no JavaScript).

**Requirements**
1. The page has a `header` with the academy name and a short tagline, a `main` containing the form, and a `footer` with contact details.
2. The form has these fields:
   - Full name (text, required, minimum 3 characters)
   - Email (email, required)
   - Password (password, required, minimum 8 characters)
   - Phone number (tel, pattern for 10 digits)
   - Date of birth (date)
   - Gender (radio buttons)
   - Country (dropdown with at least 5 options)
   - Courses of interest (checkboxes: Web Development, Data Science, AI/ML, DevOps)
   - Preferred batch timing (dropdown or radio)
   - Short statement of purpose (textarea, max 300 characters)
   - Terms and conditions (checkbox, required)
3. Group related fields using `fieldset` and `legend`.
4. Every input has a properly linked `<label>`.
5. Include Submit and Reset buttons.

**Constraints**
- Use semantic tags only. No `div`-based layouts.
- Use built-in validation attributes (`required`, `minlength`, `pattern`, `maxlength`).

**Acceptance criteria**
- Submitting with empty required fields shows the browser's validation messages.
- Clicking a label focuses its input.
- The HTML passes the W3C validator with no errors.

**Bonus**
Add a `datalist` for city suggestions and a `placeholder` on every text field.

---

## PS 2: Responsive Product Showcase Page

**Background**
A local store is launching an online catalog and needs a clean, responsive landing page that looks good on phones, tablets, and desktops.

**Objective**
Build a responsive product showcase page using HTML and CSS only.

**Requirements**
1. **Navbar**: a logo on the left and links (Home, Products, About, Contact) on the right using Flexbox. It stays fixed at the top while scrolling (`position: sticky`). On mobile, the links stack vertically below the logo.
2. **Hero section**: a full-width background image with an overlay, a heading, a subheading, and a call-to-action button with a hover effect.
3. **Product grid**: at least 8 product cards using CSS Grid. Each card has an image, name, price, short description, and "Add to Cart" button.
   - 4 columns on desktop (above 1024px)
   - 2 columns on tablet (600px to 1024px)
   - 1 column on mobile (below 600px)
4. **Card hover effect**: a slight lift (`transform`), a deeper shadow, and a smooth transition.
5. **Footer**: three columns (About, Quick Links, Contact) that stack on mobile.
6. Define colors, font sizes, and spacing as CSS variables in `:root`.

**Constraints**
- No CSS frameworks (no Bootstrap or Tailwind).
- Mobile-first approach: write base styles for mobile, then use `min-width` media queries.
- Use at least two Google Fonts or system font stacks.

**Acceptance criteria**
- No horizontal scrollbar at any width from 320px to 1920px.
- All images keep their aspect ratio (`object-fit`).
- The layout switches correctly at each breakpoint.
- Buttons and links have visible hover and focus states.

**Bonus**
Add a CSS-only hamburger menu using the checkbox hack.

---

## PS 3: Task Manager with Local Storage

**Background**
A student wants a simple task manager that remembers tasks even after the browser is closed, without needing a backend.

**Objective**
Build a to-do application using HTML, CSS, and vanilla JavaScript.

**Requirements**
1. **Add tasks**: an input and an "Add" button. Pressing Enter also adds the task. Empty or whitespace-only tasks are rejected with an inline error message (not `alert`).
2. **Task item**: each task shows its text, a checkbox to mark it complete, an edit button, and a delete button.
3. **Complete**: completed tasks get a strikethrough and a muted color.
4. **Edit**: clicking edit turns the text into an input, and Save or Escape confirms or cancels.
5. **Delete**: removes the task, with a confirmation step.
6. **Filters**: buttons for All, Active, and Completed that update the visible list.
7. **Counter**: shows "X tasks remaining" and updates live.
8. **Clear completed**: a button that removes all completed tasks at once.
9. **Persistence**: all tasks (text and completion status) are saved in `localStorage` and restored on page load.

**Technical requirements**
- Store tasks as an array of objects: `{ id, text, completed }`.
- Use event delegation for handling clicks on the task list instead of attaching a listener to every button.
- Separate your code into functions: `addTask`, `renderTasks`, `saveTasks`, `loadTasks`.
- Use `const` and `let` only (no `var`).

**Acceptance criteria**
- Refreshing the page keeps all tasks and their states.
- Adding 50 tasks does not slow down or duplicate entries.
- No console errors.
- Task text containing `<script>` or HTML is displayed as plain text (use `textContent`, not `innerHTML`).

**Bonus**
Add drag-and-drop reordering, due dates, or a dark mode toggle.

---

## PS 4: Weather Dashboard

**Background**
A travel blogger wants a small web app to check the current weather and a short forecast for any city, with a clear experience when things go wrong.

**Objective**
Build a weather app that fetches live data from a public API (such as OpenWeatherMap or Open-Meteo) using `async/await`.

**Requirements**
1. **Search**: a city input with a search button (Enter works too).
2. **Current weather card**: city and country, temperature, "feels like", condition with an icon, humidity, wind speed, and local date and time.
3. **5-day forecast**: one card per day with the date, icon, and min and max temperature.
4. **Unit toggle**: switch between °C and °F without making a new API call (convert the already-fetched data).
5. **States** (all required):
   - Loading: a spinner or skeleton while fetching
   - Error: a friendly message for "city not found", network failure, and invalid API key
   - Empty: a welcome message before the first search
6. **Recent searches**: the last 5 searched cities appear as clickable chips and are stored in `localStorage`. Duplicates are not repeated.
7. **Geolocation**: a "Use my location" button that uses the browser Geolocation API, with a fallback message if permission is denied.
8. **Dynamic UI**: the background or theme changes based on the weather condition (sunny, rainy, cloudy, night).

**Technical requirements**
- Use `fetch` with `async/await` and `try/catch`. Check `response.ok` before parsing.
- Keep the API key in a separate `config.js` file that is excluded from Git via `.gitignore`.
- Debounce the search input if you add autocomplete.
- Separate concerns into functions: `fetchWeather`, `parseData`, `renderCurrent`, `renderForecast`, `showError`.
- Disable the search button while a request is in progress to prevent duplicate calls.

**Acceptance criteria**
- Searching "London", "New Delhi", and "xyzabc" all behave correctly (success, success, handled error).
- Turning off the network shows an error message, not a blank screen.
- The app works on mobile screen sizes.
- Reloading the page still shows the recent searches.

**Bonus**
Add a temperature chart for the forecast using the Canvas API or Chart.js, and cache API responses for 10 minutes to reduce calls.