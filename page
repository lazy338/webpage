import streamlit as st
from datetime import datetime

# Sample data for articles
articles = [
    {"title": "First Article", "author": "Haniya karim ", "content": "This is the content of the first article.", "date": "2024-07-18"},
    {"title": "Second Article", "author": "hifza azam", "content": "This is the content of the second article.", "date": "2024-07-17"},
]

# Function to display articles
def display_articles():
    for article in articles:
        st.header(article['title'])
        st.subheader(f"by {article['author']} on {article['date']}")
        st.write(article['content'])
        st.write("---")

# Function to add a new article
def add_article(title, author, content):
    date = datetime.today().strftime('%Y-%m-%d')
    articles.append({"title": title, "author": author, "content": content, "date": date})

# Streamlit app layout
st.title("My Blog Page")

menu = ["Home", "Add Article"]
choice = st.sidebar.selectbox("Menu", menu)

if choice == "Home":
    st.subheader("Home")
    display_articles()
elif choice == "Add Article":
    st.subheader("Add a New Article")

    with st.form(key='article_form'):
        title = st.text_input("Title")
        author = st.text_input("Author")
        content = st.text_area("Content")
        submit_button = st.form_submit_button(label='Submit')

    if submit_button:
        add_article(title, author, content)
        st.success("Article added successfully!")
