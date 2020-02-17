# my-gantt-viewer

Online Gantt Graph based on GitHub Issues

## Usage

1. Create a project, which will be display as a project in Gantt graph.

   The project must have `EnableGantt` in the description, for example:

   ```markdown
   <!-- EnableGantt -->
   ```

2. Link issues to project. By default, the issue creation time will be used as task start time
   and issue milestone due time will be used as task due time.

   You can add modifiers in the issue body to override the behaviour:

   - `GanttStart: YYYY-MM-DD`
   - `GanttDue: YYYY-MM-DD`
   - `GanttDuration: Nd`: You can specify duration instead of due date. `d` denotes for days.
   - `GanttProgress: N%`

## Getting Started Locally

1. Copy `.env.example` to `.env`.

2. Modify `.env`:

   - Use the client ID and client secret from GitHub OAuth App.

     Note: The Authorization Callback URL of your GitHub OAuth App should be
     something like http://locahost:5000/github/callback.

   - Session secret can be generated by:

     ```bash
     openssl rand 32 | base64
     ```

3. Start by:

   ```bash
   npm install
   npm start
   ```
