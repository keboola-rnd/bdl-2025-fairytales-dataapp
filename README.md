# 🏰 Fairytales Generator

A magical Streamlit application that helps you create personalized fairytales using AI. This app allows users to input story parameters and generates custom fairytales that are stored and managed through Keboola's data platform.

## ✨ Features

- **📝 Story Creation**: Interactive form to create custom fairytales with:
  - Main character definition
  - Location selection (enchanted forests, castles, villages, etc.)
  - Main problem/challenge description
  - Inspiration from existing books
  - Target language selection (40+ languages supported)

- **📖 Story Reading**: View and read generated fairytales with:
  - Beautiful, formatted display
  - Story metadata and details
  - Real-time loading from Keboola storage

- **🎨 Beautiful UI**: Custom-styled interface with:
  - Fairytale-themed design
  - Responsive layout
  - Interactive elements with hover effects
  - Progress tracking

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- Keboola account and credentials
- Access to Keboola storage tables

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd bdl-2025-fairytales-dataapp
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up Keboola credentials**
   
   Create a `.streamlit/secrets.toml` file in your project directory:
   ```toml
   kbc_url = "your-keboola-url"
   kbc_token = "your-storage-api-token"
   ```

4. **Prepare data files**
   
   Ensure you have the required CSV file:
   - `in/tables/books.csv` - Contains book data for inspiration selection

5. **Run the application**
   ```bash
   streamlit run fairytales_generator.py
   ```

## 📁 Project Structure

```
bdl-2025-fairytales-dataapp/
├── fairytales_generator.py    # Main Streamlit application
├── requirements.txt           # Python dependencies
├── README.md                 # This file
├── LICENSE                   # License file
└── in/
    └── tables/
        └── books.csv         # Book data for inspiration
```

## 🎯 Usage

### Creating a Story

1. **Navigate to the "📝 Create Story" tab**
2. **Fill in the story parameters**:
   - **Main Character**: Describe your hero (name, characteristics, etc.)
   - **Location**: Choose from predefined locations or add custom ones
   - **Main Problem**: Describe the challenge or adventure
   - **Inspiration**: Select a book for creative inspiration
   - **Target Language**: Choose the language for your fairytale

3. **Click "💾 Generate Fairytale"** to save your story configuration

### Reading Stories

1. **Navigate to the "📖 Read Stories" tab**
2. **Click "🔄 Load Latest Fairytale"** to fetch the most recent story
3. **Enjoy reading** your generated fairytale with beautiful formatting

## 🔧 Configuration

### Keboola Integration

The app integrates with Keboola for data storage and management:

- **Input Table**: `in.c-generator-data.story` - Stores story configurations
- **Output Table**: `out.c-fairytale-ai-pipeline.story` - Contains generated fairytales
- **Books Data**: `in/tables/books.csv` - Reference data for inspiration

### Environment Variables

The application requires the following secrets to be configured:

- `kbc_url`: Your Keboola instance URL
- `kbc_token`: Your Keboola Storage API token

## 🎨 Customization

### Adding New Locations

Edit the location options in the `location` selectbox (line 108):

```python
location = st.selectbox(
    "Location",
    ["Enchanted Forest", "Royal Castle", "Your New Location", ...],
    # ... rest of configuration
)
```

### Adding New Languages

Extend the language list in the `target_language` selectbox (line 142):

```python
target_language = st.selectbox(
    "Target Language",
    ["English", "Spanish", "Your New Language", ...],
    # ... rest of configuration
)
```

### Styling

The app uses custom CSS for theming. Modify the styles in the `st.markdown()` section (lines 55-86) to customize the appearance.

## 🐛 Troubleshooting

### Common Issues

1. **Keboola Connection Error**
   - Verify your credentials in `.streamlit/secrets.toml`
   - Check that your Keboola URL and token are correct
   - Ensure you have proper permissions for the required tables

2. **Missing Books Data**
   - Ensure `in/tables/books.csv` exists and contains the required columns
   - Check that the CSV has `title` and `book_id` columns

3. **Table Not Found**
   - Verify that the required Keboola tables exist
   - Check table names and permissions

### Error Messages

- `❌ Failed to initialize Keboola connection`: Check your credentials
- `❌ Keboola connection not available`: Verify your configuration
- `📭 No fairytales found`: Generate some stories first or check table existence

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the terms specified in the LICENSE file.

## 🧚‍♀️ Acknowledgments

- Built with [Streamlit](https://streamlit.io/)
- Data management powered by [Keboola](https://www.keboola.com/)
- Inspired by the magic of storytelling and fairytales

---

*Created with magic and Streamlit* 🧚‍♀️
