# Octobass

Octobass is a simple, single-page social feed application built with vanilla HTML/JS and Supabase. It allows users to post short messages and view a feed of recent posts. It includes basic moderation features (deletion with a password) and a dark mode.

## Features

*   **Public Feed**: View the 50 most recent posts.
*   **Post Creation**: Submit new text posts to the feed.
*   **Real-time Updates**: The feed updates automatically when new posts are added.
*   **Secure Deletion**: Admin-level deletion of posts using a password via a secure Supabase RPC function.
*   **Theming**: Toggle between Light and Dark modes.
*   **Responsive Design**: Works on mobile and desktop.

## Setup

1.  **Clone the repository**:
    ```bash
    git clone <repository-url>
    cd octobass
    ```

2.  **Configuration**:
    The application is configured to connect to a Supabase instance. The configuration constants are located in `index.html` within the `<script>` tag:
    *   `SUPABASE_URL`: The URL of your Supabase project.
    *   `SUPABASE_KEY`: The public API key (anon key).

    *Note: The current configuration points to a demo Supabase instance. To use your own backend, you will need to update these values.*

3.  **Supabase Database Schema**:
    If setting up your own Supabase project, you need a table named `posts` with the following columns:
    *   `id` (int8, primary key)
    *   `content` (text)
    *   `created_at` (timestamptz, default now())

    And a stored procedure (RPC) named `delete_post_with_password` that accepts `post_id` and `secret_pass`.

## Usage

*   **Open the App**: Simply open `index.html` in your web browser. No build server is required.
*   **Posting**: Type your message in the text area and click "Post".
*   **Deleting**: Click the "x" button on a post. You will be prompted for an admin password.
*   **Toggle Theme**: Click the moon/sun icon in the top right corner to switch themes.

## Development

The code is contained entirely within `index.html`.
*   **CSS**: Styles are in the `<style>` block.
*   **JS**: Logic is in the `<script>` block, utilizing the Supabase JS client via CDN.

## License

MIT
