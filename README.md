# Screen Control Definition Format (scdf)
A format that allows for a standard way to describe a user interface for efficient AI screen control. It can describe any app regardless of platform (Windows, Linux, Web, etc).

It can describe:

- Location of buttons
- Functionality of a certain window
- Links/connections between different windows

And it's not just read-only. An AI screen control app could also update the SCDF (either locally or on a hosted database) if it encounters a new UI with primative information.

**Draft 1 is available**
Features:
* Applications & Windows
* Controls (buttons, inputs, lists, etc.)
* Control location & type
* Events/actions associated with controls
* Links between windows (navigation, relationships)
* Metadata (AI-detected vs human-defined, timestamps, notes)

An example of how it would work:
* An AI agent detects a new app window → inserts into `scdf_windows`
* It scans for buttons → inserts into `scdf_controls`
* It sees a "Login" button that opens a new window → inserts into `scdf_window_links`
* It describes what the button does → `scdf_control_events`
* AI logs an annotation for low confidence → `scdf_annotations`
