# Invoice Generator

## Overview

The Invoice Generator is a Python application that uses Tkinter for the user interface and `docxtpl` for generating invoice documents. This application allows users to create and manage invoices, add items to the invoice, and generate a formatted invoice document based on a predefined template.

## Features

- **Add Items**: Enter details for each item including quantity, description, and unit price.
- **Generate Invoice**: Create a new invoice based on entered details and save it as a Word document (`.docx`).
- **New Invoice**: Reset the form and clear the invoice list to start a new invoice.

## Requirements

- Python 3.x
- `tkinter` (usually included with Python)
- `docxtpl` (install using `pip install docxtpl`)

## Getting Started

### Installation

1. Clone or download this repository to your local machine.
2. Install the required Python packages:

    ```bash
    pip install docxtpl
    ```
    
    ```bash
    pip install tk
    ```

### Usage

1. Ensure that you have an `invoice_template.docx` file in the same directory as the script. This template should be formatted with placeholders that match the keys used in the `render` method.

2. Run the script:

    ```bash
    python main.py
    ```

3. The application window will open. Fill in the details for the customer and items:
   - **First Name**: Enter the customer's first name.
   - **Last Name**: Enter the customer's last name.
   - **Phone**: Enter the customer's phone number.
   - **Quantity**: Enter the quantity of the item.
   - **Description**: Enter a description of the item.
   - **Unit Price**: Enter the price per unit of the item.

4. Click **Add Item** to add the item to the invoice list.

5. Click **Generate Invoice** to create and save the invoice document. A message will confirm when the invoice is complete.

6. Click **New Invoice** to clear the form and start fresh.

## Template Structure

The `invoice_template.docx` should include placeholders for the following fields:

- `name` (e.g., "Ramesh")
- `phone` (e.g., "12345-67890")
- `invoice_list` (list of items with details)
- `subtotal` (total before tax)
- `salestax` (percentage of tax applied)
- `total` (final amount including tax)

## Example

Here is an example of how the template placeholders might look in your `invoice_template.docx`:

```plaintext
Invoice for: {{ name }}
Phone: {{ phone }}

Items:
{% for item in invoice_list %}
  Quantity: {{ item[0] }}
  Description: {{ item[1] }}
  Unit Price: {{ item[2] }}
  Total: {{ item[3] }}
{% endfor %}

Subtotal: {{ subtotal }}
Sales Tax: {{ salestax }}
Total Amount: {{ total }}
