# Java Swing Practical: Campus Café Ordering System
---
## 1. Activity Overview
### Scenario

Your campus has opened a small café where students can order meals during breaks. Currently, the café records orders manually, which can lead to incorrect orders and unnecessary delays.
You have been asked to develop a **Campus Café Ordering System** using Java Swing.
The application must allow a café employee to enter a customer's details, select a meal, choose a meal size, indicate whether the order is takeaway, and generate an order summary.

You must use the **NetBeans GUI Builder (Design view)** to create the interface. You are not required to create the visual layout by writing Java code. Instead, drag and drop components from the Palette and configure their properties. You will write Java code to implement the application's functionality.

### Learning Outcomes

By completing this activity, you should be able to:

- Create a Java application using a `JFrame Form` in NetBeans.
- Design a graphical user interface using drag-and-drop components.
- Use labels, text fields, radio buttons, checkboxes, combo boxes and text areas.
- Create a menu bar with functional menu items.
- Retrieve information entered or selected by a user.
- Use event handling to respond to button clicks and menu selections.
- Display an order summary in a text area.
- Apply basic input validation and test an application.

---

## 2. Application Requirements

Your application must include the following components and functionality:

| Component | Requirement |
|---|---|
| `JFrame` | Main window titled Campus Café Ordering System |
| `JMenuBar` | Contains File and Help menus |
| `JMenuItem` | Contains Clear Form, Exit and About options |
| `JLabel` | Identifies each field on the form |
| `JTextField` | Captures the customer's name |
| `JComboBox` | Allows the user to select a meal |
| `JRadioButton` | Allows the user to choose Small, Regular or Large |
| `JCheckBox` | Allows the user to select Takeaway |
| `JTextArea` | Displays the order summary |
| `JButton` | Generates the order summary |
| `JButton` | Clears the form |

**Expected behaviour:** The user enters a name, selects a meal and size, optionally selects Takeaway, and clicks Generate Order. The application validates the input and displays the order details in the text area.

---

# Part A: Create the NetBeans Project

## Step 1: Create a New Java Project

1. Open Apache NetBeans.
2. Select **File → New Project**.
3. Select the Java category and choose the standard Java Application project option available in your NetBeans version.
4. Click **Next**.
5. Enter the project name: `CampusCafeOrderingSystem`.
6. Select a suitable project location.
7. If NetBeans offers an option to create a main class automatically, you may leave it unchecked because you will create a JFrame Form.
8. Click **Finish**.

**Checkpoint:** Your project should appear in the Projects window.

## Step 2: Create a JFrame Form

1. Right-click your project or its source package.
2. Select **New → JFrame Form**.
3. Enter the class name: `CampusCafeForm`.
4. Select or create a package named `campuscafe`.
5. Click **Finish**.

NetBeans should open the form with two views:

- **Design:** Used to arrange components visually.
- **Source:** Used to write application logic.

For this activity, use Design view for the interface. Do not manually write the layout code that NetBeans generates.

---

# Part B: Design the User Interface

## Step 3: Configure the Main Window

1. Select the form in Design view.
2. Open the Properties window.
3. Locate the `title` property and set it to `Campus Café Ordering System`.
4. If available, set `defaultCloseOperation` to `EXIT_ON_CLOSE`.
5. Resize the form so that all components can be displayed comfortably.

## Step 4: Add a Heading

1. Locate `JLabel` in the Palette.
2. Drag a label to the top of the form.
3. Change its text property to `CAMPUS CAFÉ ORDERING SYSTEM`.
4. Rename the variable to `lblHeading`.
5. Increase the font size or make the text bold using the Properties window.

## Step 5: Add Customer Details

Drag the following components onto the form:

| Component | Displayed text | Variable name |
|---|---|---|
| `JLabel` | Customer Name: | `lblCustomerName` |
| `JTextField` | Leave empty | `txtCustomerName` |

To rename a component, right-click it and select **Change Variable Name**, or use the relevant Code properties in your NetBeans version.

Arrange the label and text field neatly.

**Checkpoint:** You should be able to enter a customer's name when the application runs.

## Step 6: Add Meal Selection

1. Drag a `JLabel` onto the form, set its text to `Select Meal:`, and rename it `lblMeal`.
2. Drag a `JComboBox` onto the form and rename it `cmbMeal`.
3. Select the combo box and open the Properties window.
4. Locate the `model` property and open its editor, usually by clicking the ellipsis button.
5. Replace the default values with:
   - Burger
   - Pizza
   - Pasta
   - Chicken Wrap
   - Sandwich
6. Confirm the changes.

**Checkpoint:** The combo box should contain five meal options.

## Step 7: Add Meal-Size Radio Buttons

The café offers meals in three sizes.

1. Add a `JLabel` with the text `Meal Size:`.
2. Drag three `JRadioButton` components onto the form.
3. Configure them as follows:

| Displayed text | Variable name |
|---|---|
| Small | `rdoSmall` |
| Regular | `rdoRegular` |
| Large | `rdoLarge` |

### Group the Radio Buttons

The customer must choose only one meal size.

1. Locate `ButtonGroup` in the Palette.
2. Drag it onto the form. It is a non-visual component and will appear in the component area.
3. Select `rdoSmall` and set its `buttonGroup` property to the group you created.
4. Repeat for `rdoRegular` and `rdoLarge`.
5. Set `rdoRegular` as selected by default, if appropriate for your design.

**Checkpoint:** Selecting Large should automatically deselect Small or Regular.

## Step 8: Add the Takeaway Checkbox

1. Drag a `JCheckBox` onto the form.
2. Set its text to `Takeaway`.
3. Rename it `chkTakeaway`.
4. Leave it unchecked by default.

For this activity, an unchecked box means the order is **Dine In**, while a checked box means **Takeaway**.

## Step 9: Add Action Buttons

Drag two `JButton` components onto the form:

| Button text | Variable name | Purpose |
|---|---|---|
| Generate Order | `btnGenerateOrder` | Validates input and displays the order |
| Clear Form | `btnClearForm` | Resets the form |

Arrange the buttons neatly underneath the order details.

## Step 10: Add the Order Summary Area

1. Add a `JLabel` with the text `ORDER SUMMARY`.
2. Drag a `JTextArea` onto the form and rename it `txtOrderSummary`.
3. Set its `editable` property to `false`.
4. Place it inside a `JScrollPane` if NetBeans has not already created one.
5. Position the summary area so it is easy to read.

The text area should initially be empty.

---

# Part C: Create the Application Menu

## Step 11: Add a Menu Bar

1. Locate `Menu Bar` or `JMenuBar` in the Palette.
2. Drag it onto the form.
3. You will then see File and Edit on the Menu bar by default
4. Under File, add two menu items (right click on "File" to add your first item, select Add from palette, select Menu Item) ; **Clear Form** and **Exit**.
5. Under Edit, add **About**.

Rename the menu items as follows:

| Menu item | Variable name |
|---|---|
| Clear Form | `mnuClearForm` |
| Exit | `mnuExit` |
| About | `mnuAbout` |

**Checkpoint:** Run the application and verify that the menu bar appears. The menu items do not need to perform actions yet.

---

# Part D: Add the Application Logic

## Step 12: Generate the Order Summary

1. Open Design view.
2. Double-click the Generate Order button.
3. NetBeans should generate an `actionPerformed` event handler.
4. Add the following code inside the generated method.

Do not replace the entire form class or modify guarded code generated by NetBeans.

```java
String customerName = txtCustomerName.getText().trim();

// Validate the customer name
if (customerName.isEmpty()) {
    JOptionPane.showMessageDialog(
        this,
        "Please enter the customer's name."
    );
    txtCustomerName.requestFocus();
    return;
}

// Get the selected meal
String meal = (String) cmbMeal.getSelectedItem();

// Get the selected size
String mealSize = "";

if (rdoSmall.isSelected()) {
    mealSize = "Small";
} else if (rdoRegular.isSelected()) {
    mealSize = "Regular";
} else if (rdoLarge.isSelected()) {
    mealSize = "Large";
}

// Get the order type
String orderType;

if (chkTakeaway.isSelected()) {
    orderType = "Takeaway";
} else {
    orderType = "Dine In";
}

// Build the order summary
String summary =
    "========== CAMPUS CAFE ==========\n\n"
    + "Customer: " + customerName + "\n"
    + "Meal: " + meal + "\n"
    + "Meal Size: " + mealSize + "\n"
    + "Order Type: " + orderType + "\n\n"
    + "Thank you for your order!\n"
    + "================================\n";

// Display the summary
txtOrderSummary.setText(summary);
```

### Understand the Code

- `getText()` retrieves the name entered into the text field.
- `trim()` removes unnecessary spaces at the beginning and end.
- `isEmpty()` checks whether the customer name is empty.
- `getSelectedItem()` retrieves the selected meal.
- `isSelected()` checks whether a radio button or checkbox is selected.
- `setText()` displays the generated summary in the text area.
- `return` stops the event handler when validation fails.

**Important:** The code assumes the component variable names match those in the instructions. If your names differ, update the code accordingly.

## Step 13: Add Clear Form Functionality

1. Return to Design view.
2. Double-click the Clear Form button.
3. Add the following code inside its generated event handler:

```java
txtCustomerName.setText("");

cmbMeal.setSelectedIndex(0);

rdoSmall.setSelected(false);
rdoRegular.setSelected(true);
rdoLarge.setSelected(false);

chkTakeaway.setSelected(false);

txtOrderSummary.setText("");

txtCustomerName.requestFocus();
```

This restores the form to its initial state, with Regular selected as the default meal size.

The Clear Form menu item should perform the same action. For better programming practice, create a reusable `clearForm()` method and call it from both event handlers.

## Step 14: Add File Menu Actions

### Exit

1. Open Design view.
2. Double-click the Exit menu item.
3. Add:

```java
System.exit(0);
```

This closes the application.

### About

1. Double-click the About menu item.
2. Add:

```java
JOptionPane.showMessageDialog(
    this,
    "Campus Café Ordering System\n"
    + "Developed as a Java Swing practical.",
    "About",
    JOptionPane.INFORMATION_MESSAGE
);
```

This displays an information dialog.

### Clear Form Menu Item

Double-click the Clear Form menu item and make it reset the form in the same way as the Clear Form button. Reuse the `clearForm()` method rather than duplicating the same logic.

---

# Part E: Run and Test the Application

## Step 15: Run the Application

1. Save your project.
2. Click the Run Project button.
3. Confirm that the window opens correctly.
4. Enter a customer's name.
5. Select a meal from the combo box.
6. Select a meal size.
7. Select or leave the Takeaway checkbox unchecked.
8. Click Generate Order.
9. Check whether the order summary appears in the text area.

## Step 16: Complete the Test Cases

Test each scenario and record the outcome.

| Test | Action | Expected result |
|---|---|---|
| 1 | Enter a name and generate an order | Order summary appears |
| 2 | Leave the name blank | Validation message appears |
| 3 | Select Pizza | Summary displays Pizza |
| 4 | Select Large | Summary displays Large |
| 5 | Select Takeaway | Summary displays Takeaway |
| 6 | Leave Takeaway unchecked | Summary displays Dine In |
| 7 | Click Clear Form | Inputs and summary reset |
| 8 | Select File → Exit | Application closes |
| 9 | Select Help → About | Information dialog appears |

If a test fails, identify the cause, correct the problem and repeat the test.

---

# Part F: Reflective Questions

Answer the following questions in your own words.

1. What is the difference between a `JTextField` and a `JTextArea`?
2. Why do we use a `ButtonGroup` with radio buttons?
3. What is the difference between a `JCheckBox` and a `JRadioButton`?
4. What is the purpose of an `ActionListener`?
5. Why is input validation important?
6. Why is the order summary text area set to non-editable?
7. What is the difference between designing a form in NetBeans Design view and writing its event-handling code?
8. Why should the same Clear Form logic ideally be placed in a reusable method?
9. What could happen if the application tries to generate an order without validating the customer's input?
10. How could the application be improved to make it more useful to a real café?

---

# Part G: Extension Challenges

Once the basic application works, attempt the following improvements.

### Challenge 1: Add Meal Prices

Assign a price to each meal and display the price in the order summary.

Example prices:

- Burger: R55.00
- Pizza: R75.00
- Pasta: R65.00
- Chicken Wrap: R50.00
- Sandwich: R40.00

### Challenge 2: Calculate the Total

Add a price adjustment for meal size:

- Small: no additional charge
- Regular: R10.00 extra
- Large: R20.00 extra

Calculate the total and display it in the order summary.

### Challenge 3: Add Another Checkbox

Add a checkbox called Extra Cheese. If selected, include Extra Cheese in the order summary.

### Challenge 4: Improve the Validation

Ensure that a meal size has been selected before generating the order.

### Challenge 5: Add a Receipt File

Add a Save Receipt button that saves the generated order summary to a text file. Use exception handling to manage file-writing errors.

### Challenge 6: Improve the User Interface

Use panels and appropriate layout managers to make the form look professional. Align labels and input fields consistently, and make the summary easy to read.

---

**Final instruction:** Your application must be your own work. You may consult your lecture notes and Java documentation, but ensure you understand the purpose of every component and every line of event-handling code you submit.
