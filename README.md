# Currency Multiplier Calculator

A user-friendly, client-side tool to calculate currency values based on multipliers against a base USD value. This tool features two separate tables for different currency lists ('LVC' and 'Standard'), with dynamic calculations and interactive sorting.

https://hrxtreme.github.io/CurrencyMultiplier/
 
<img width="1345" height="632" alt="image" src="https://github.com/user-attachments/assets/1448a68a-96f5-4b0c-87c5-8fdf2e0eb37e" />


---

## Features

-   **Dual Table Layout:** Manage and view two independent lists of currencies simultaneously.
-   **Dynamic Calculation:** Instantly calculates "Min Bet," "Default Bet," and "Maximum Bet" values as you type in the base USD amounts.
-   **Interactive Sorting:** Sort each table by Currency Name or Multiplier. Click a header to cycle through ascending, descending, and default order.
-   **Reset Functionality:** Easily revert the sorting for each table to its original order with a single "Reset Sort" click.
-   **Clean, Responsive Design:** A modern UI built with Tailwind CSS that works well on various screen sizes.
-   **Informative Tooltips:** Hover over special currencies (marked with a `*`) for more details on their unique multiplier rules.
-   **Self-Contained:** Runs entirely in the browser with no server-side dependencies. Just open the HTML file.

---

## How to Use

1.  **Download the Project:**
    Save the HTML file to your local machine.

2.  **Open in Browser:**
    Open the `index.html` (or the renamed file) in any modern web browser like Chrome, Firefox, or Edge.

3.  **Enter Base Values:**
    In the highlighted `USD` row for either table, enter the base values for **Min Bet**, **Default Bet**, and **Maximum Bet**.

4.  **View Results:**
    The corresponding values for all other currencies in that table will update automatically.

5.  **Sort Data:**
    Click on the **Currency** or **Multiplier** headers to sort the data. Clicking the same header repeatedly will cycle through ascending, descending, and the original order.

---

## Customization

You can easily customize the currency lists by editing the JavaScript arrays directly within the HTML file.

1.  **Locate the Data Arrays:**
    Inside the `<script>` tag, find the `originalLvcCurrencies` and `originalStandardCurrencies` arrays.

2.  **Add or Edit Currencies:**
    Modify the arrays by adding, removing, or editing the currency objects. Each object follows this structure:

    ```javascript
    { 
        name: 'USD - United States Dollar', 
        multiplier: 1, 
        symbol: '$',
        symbolPosition: 'after', // Optional: 'after' or undefined (defaults to before)
        tooltip: 'This is a tooltip.' // Optional
    }
    ```

3.  **Special Multipliers:**
    For currencies with different multipliers for min/max bets (like CNY), use an object for the `multiplier` property:
    ```javascript
    { 
        name: 'CNY - Yuan Renminbi *', 
        multiplier: { min: 5, def: 5, max: 10 }, 
        displayMultiplier: '5/10', // Text to show in the table
        symbol: '¥', 
        tooltip: 'Uses a multiplier of 5 for Min/Default and 10 for Max.' 
    }
    ```

---

## Technologies Used

-   **HTML5:** For the core structure of the application.
-   **Tailwind CSS:** For all styling and layout, loaded via CDN.
-   **JavaScript (ES6+):** For all application logic, including calculations, sorting, and DOM manipulation.
