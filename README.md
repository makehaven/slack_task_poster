Slack Task Poster Module for Drupal 10

Overview:
-------------
The Slack Task Poster module integrates Drupal 10 with Slack by sending instant notifications when a new Task node is created. This module no longer relies on the legacy Rules system—instead, it uses Drupal's core entity hooks. Notifications are posted to a default Slack channel (#tasks) and can include additional channels based on related item fields and taxonomy term settings. The module also mentions the task author using their Slack ID or full name.

Features:
-------------
• Instant Notifications: Automatically sends Slack messages when a new Task is created.
• User Mentions: Notifies the task creator by referencing their Slack username (if available) or by using their first and last name.
• Multiple Channel Support: Posts to a default channel (#tasks) and additional channels determined by associated items or taxonomy terms.
• Task Linking: Includes a direct link to the Task node on your Drupal site.
• Centralized Slack Configuration: Retrieves the Slack webhook URL from the Slack Connector module for unified management across Slack integrations.

Installation:
-------------
1. Place the Slack Task Poster module folder in your Drupal custom modules directory (e.g., modules/custom/slack_task_poster).
2. Ensure the Slack Connector module is installed, enabled, and configured with your Slack webhook URL.
3. Enable the Slack Task Poster module through the Drupal admin interface.
4. Create new Task nodes to trigger Slack notifications.

Configuration:
-------------
• Slack Webhook URL: Managed by the Slack Connector module. Configure it at /admin/config/services/slack-connector.
• Default Slack Channel: The module uses #tasks as the default channel. Additional channels can be added via referenced Item fields or taxonomy terms.
• Required Fields:
  - Task Nodes: Should have a title and (optionally) a body.
  - Author: User profiles must include either a Slack ID (field_member_slack_id_number) or first and last name fields (field_first_name and field_last_name).
  - Referenced Items: If a Task references an Item (via field_task_equipment), the Item can define its own Slack channel using field_item_slack_channel. Additionally, taxonomy terms on the Item (via field_item_area_interest) may provide Slack channel names via field_interest_slack_channel.

Usage:
-------------
Once installed and configured, every new Task node will trigger an automatic Slack notification. The notification message includes:
• The task title and an excerpt from the body text.
• A mention of the task creator.
• A direct link to view the Task on your site.
• The Slack channels to which the notification is sent.

Support:
-------------
For further support or questions regarding configuration and usage, please consult your Drupal development team or refer to additional project documentation.
