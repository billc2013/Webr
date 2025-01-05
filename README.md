# Local WebR REPL

This project is a web-based R REPL (Read-Eval-Print Loop) built using [WebR](https://webr.r-wasm.org/). It allows users to execute R code directly in the browser, upload CSV files for analysis, and generate plots dynamically.

## Features

1. **Run R Code Directly in Browser**:
   - A simple interface to input R commands and view the results

2. **Upload CSV Files**:
   - Upload CSV files for analysis in R
   - Automatically detects and parses date strings (e.g., `YYYY-MM-DD`)

3. **Generate Plots**:
   - Generate and display PNG plots based on the uploaded data
   - Automatically handles numeric and date-based data

4. **Responsive Design**:
   - The interface adjusts to fit various screen sizes

## Getting Started

### Prerequisites

1. **Modern Browser**:
   - Ensure your browser supports WebAssembly (WASM) and ES6 modules (e.g., Chrome, Firefox, Edge)

2. **Hosting**:
   - Use a local development server or a hosting platform like Netlify to serve the files, as Cross-Origin Isolation is required for WebR

### Setup

1. Clone this repository:
```bash
git clone https://github.com/yourusername/webr-repl.git
cd webr-repl
```

2. Start a local server:
```bash
python3 -m http.server
```

3. Open `http://localhost:8000` in your browser

## Usage

### Run R Code
- Enter any valid R code (e.g., `1 + 1`, `summary(cars)`) in the input box and click "Run"

### Upload a CSV File
- Click the "Choose File" button and upload a `.csv` file (e.g., `temperature_data.csv`)

### Display Data or Generate Plot
After uploading a file:
- Click "Display Head" to view the first few rows of the dataset
- Click "Create Plot" to generate a PNG plot of the data

### View Plot
The generated plot will appear as an image below the REPL output

## Example CSV File: temperature_data.csv

Here's an example CSV file you can use to test the application:

```csv
Date,Temperature
2025-01-01,3.2
2025-01-02,4.1
2025-01-03,2.8
2025-01-04,3.5
2025-01-05,4.0
2025-01-06,3.9
2025-01-07,5.2
```

## Technical Overview

### HTML
Provides the interface for:
- Inputting R code
- Uploading CSV files
- Displaying results and plots

### JavaScript
1. **WebR Initialization**:
   - Initializes WebR for running R code in the browser

2. **File Handling**:
   - Processes uploaded CSV files and passes them to R

3. **Plotting**:
   - Generates and displays PNG plots using the R `png()` function

4. **Error Handling**:
   - Provides detailed error messages for debugging invalid inputs or unsupported operations

## Known Issues

1. **Cross-Origin Isolation**:
   - Ensure the project is served from a properly configured server to enable WebR functionality

2. **File Size Limits**:
   - Large CSV files may take longer to process or fail due to memory limitations in the browser

## Future Enhancements

1. **Dynamic Column Selection**:
   - Allow users to select specific columns for plotting

2. **Support for Additional File Formats**:
   - Expand support to `.txt` and `.json` files

3. **Improved Plot Customization**:
   - Add user controls for customizing plot aesthetics (e.g., colors, labels)

4. **Persistent State**:
   - Cache uploaded files in the browser for reuse

## Contributing

1. Fork the repository
2. Create a new branch (`git checkout -b feature-name`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature-name`)
5. Open a pull request

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
