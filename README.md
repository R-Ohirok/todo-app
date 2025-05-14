This project is a full-featured Todo application with API integration, real-time UI feedback, and robust error handling. It supports creating, editing, updating, deleting, and filtering todos while providing a responsive and user-friendly experience.

➕ Adding Todos
Users can add new todos through a form with a focused input field. When submitted:

- The title is trimmed before being sent to the API.

- A temporary todo with a loading indicator appears immediately.

- After a successful response, the new todo is added to the main list.

- In case of failure, an error notification is shown and the input value is preserved.

- The input is cleared and re-focused on success.

- If the input is empty, a warning notification (Title should not be empty) is shown instead of sending a request.

🔍 Todo Filtering
Todos can be filtered by their completion status:

- All todos are shown by default.

- Active displays only incomplete todos.

- Completed shows todos marked as finished.

- The currently selected filter is visually highlighted using the selected class for better UX.

🗑️ Deleting Todos
Todos can be deleted individually or in bulk:

- When a todo is deleted, a loader is shown until the API responds.

- On success, the todo is removed from the list.

- On failure, the todo remains visible and an error notification (Unable to delete a todo) is displayed.

- Completed todos can be cleared all at once using the Clear completed button, which triggers multiple parallel delete requests. Successful deletions are processed individually, while any failures show appropriate error messages without affecting other deletions.

✔️ Toggling Todo Status
Each todo item supports toggling its completed status:

- A loading overlay is shown while the status is being updated.

- The status change is confirmed only after a successful API response.

- If the request fails, the UI is reverted and a notification (Unable to update a todo) is shown.

The application also supports toggling all todos at once via a toggleAll checkbox:

- The checkbox reflects the global completion state and applies bulk status changes.

- Only todos that require a change are updated.

- Each change is handled as an individual API request to maintain responsiveness and allow partial success.

✏️ Editing Todos
Todo titles can be edited inline with intuitive interactions:

- Double-clicking a title opens an editable input field.

- Edits are saved on Enter or when the input loses focus (onBlur).

- Changes are discarded if the new title matches the old one or if the user presses Escape.

- An empty new title is treated as a delete action.

- A loader is shown during API communication.

🚨 Error Notifications
The application provides real-time error feedback through notifications displayed at the bottom of the screen. Notifications appear when any API request fails and can be dismissed manually using a close button. They also disappear automatically after 3 seconds and are cleared before any new request is sent.