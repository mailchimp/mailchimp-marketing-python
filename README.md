<p align="center">
  <a href="https://mailchimp.com/developer/">
    <img src="https://raw.githubusercontent.com/mailchimp/mailchimp-client-lib-codegen/master/resources/images/mcdev-banner.png" alt="Mailchimp Developer" width="100%" height="auto">
  </a>
</p>

# Mailchimp Marketing — Python

The official Python client library for the Mailchimp Marketing API

## Requirements.

Python 2.7 and 3.4+

## Installation & Usage
### pip install

If the python package is hosted on GitHub, you can install directly from GitHub

```sh
pip install git+https://github.com/mailchimp/mailchimp-marketing-python.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/mailchimp/mailchimp-marketing-python.git`)

Then import the package:
```python
import mailchimp_marketing
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import mailchimp_marketing
```

## Quick Start

Please follow the [installation procedure](#installation--usage) and then run the following:

```python
import mailchimp_marketing as MailchimpMarketing
from mailchimp_marketing.api_client import ApiClientError

try:
  client = MailchimpMarketing.Client()
  client.set_config({
    "api_key": "YOUR_API_KEY",
    "server": "YOUR_SERVER_PREFIX"
  })
  response = client.ping.get()
  print(response)
except ApiClientError as error:
  print(error)
```

## Authentication Methods

The client library can be configured to use either **Basic Auth** or **OAuth2**.

For either method, a server prefix should be passed in i.e. `us19`, in order for the client to determine to appropriate host url.

### Basic Auth
```python
client.set_config({
  "api_key": "YOUR_API_KEY",
  "server": "YOUR_SERVER_PREFIX"
})
```

### OAuth2
```python
client.set_config({
  "access_token": "YOUR_ACCESS_TOKEN",
  "server": "YOUR_SERVER_PREFIX"
})
```

## API Endpoints

All URIs are relative to *https://server.api.mailchimp.com/3.0*

| Method | Endpoint |
| ---------- | -------- |
| **activityFeed.get_chimp_chatter** | /activity-feed/chimp-chatter |
| **authorizedApps.list** | /authorized-apps |
| **authorizedApps.get** | /authorized-apps/{app_id} |
| **authorizedApps.link** | /authorized-apps |
| **automations.archive** | /automations/{workflow_id}/actions/archive |
| **automations.delete_workflow_email** | /automations/{workflow_id}/emails/{workflow_email_id} |
| **automations.list** | /automations |
| **automations.get** | /automations/{workflow_id} |
| **automations.list_all_workflow_emails** | /automations/{workflow_id}/emails |
| **automations.get_workflow_email** | /automations/{workflow_id}/emails/{workflow_email_id} |
| **automations.get_workflow_email_subscriber_queue** | /automations/{workflow_id}/emails/{workflow_email_id}/queue |
| **automations.get_workflow_email_subscriber** | /automations/{workflow_id}/emails/{workflow_email_id}/queue/{subscriber_hash} |
| **automations.list_workflow_email_subscribers_removed** | /automations/{workflow_id}/removed-subscribers |
| **automations.get_removed_workflow_email_subscriber** | /automations/{workflow_id}/removed-subscribers/{subscriber_hash} |
| **automations.update_workflow_email** | /automations/{workflow_id}/emails/{workflow_email_id} |
| **automations.create** | /automations |
| **automations.pause_all_emails** | /automations/{workflow_id}/actions/pause-all-emails |
| **automations.start_all_emails** | /automations/{workflow_id}/actions/start-all-emails |
| **automations.pause_workflow_email** | /automations/{workflow_id}/emails/{workflow_email_id}/actions/pause |
| **automations.start_workflow_email** | /automations/{workflow_id}/emails/{workflow_email_id}/actions/start |
| **automations.add_workflow_email_subscriber** | /automations/{workflow_id}/emails/{workflow_email_id}/queue |
| **automations.remove_workflow_email_subscriber** | /automations/{workflow_id}/removed-subscribers |
| **batchWebhooks.remove** | /batch-webhooks/{batch_webhook_id} |
| **batchWebhooks.get** | /batch-webhooks/{batch_webhook_id} |
| **batchWebhooks.list** | /batch-webhooks |
| **batchWebhooks.update** | /batch-webhooks/{batch_webhook_id} |
| **batchWebhooks.create** | /batch-webhooks |
| **batches.delete_request** | /batches/{batch_id} |
| **batches.list** | /batches |
| **batches.status** | /batches/{batch_id} |
| **batches.start** | /batches |
| **campaignFolders.remove** | /campaign-folders/{folder_id} |
| **campaignFolders.list** | /campaign-folders |
| **campaignFolders.get** | /campaign-folders/{folder_id} |
| **campaignFolders.update** | /campaign-folders/{folder_id} |
| **campaignFolders.create** | /campaign-folders |
| **campaigns.remove** | /campaigns/{campaign_id} |
| **campaigns.delete_feedback_message** | /campaigns/{campaign_id}/feedback/{feedback_id} |
| **campaigns.list** | /campaigns |
| **campaigns.get** | /campaigns/{campaign_id} |
| **campaigns.get_content** | /campaigns/{campaign_id}/content |
| **campaigns.get_feedback** | /campaigns/{campaign_id}/feedback |
| **campaigns.get_feedback_message** | /campaigns/{campaign_id}/feedback/{feedback_id} |
| **campaigns.get_send_checklist** | /campaigns/{campaign_id}/send-checklist |
| **campaigns.update** | /campaigns/{campaign_id} |
| **campaigns.update_feedback_message** | /campaigns/{campaign_id}/feedback/{feedback_id} |
| **campaigns.create** | /campaigns |
| **campaigns.cancel_send** | /campaigns/{campaign_id}/actions/cancel-send |
| **campaigns.create_resend** | /campaigns/{campaign_id}/actions/create-resend |
| **campaigns.pause** | /campaigns/{campaign_id}/actions/pause |
| **campaigns.replicate** | /campaigns/{campaign_id}/actions/replicate |
| **campaigns.resume** | /campaigns/{campaign_id}/actions/resume |
| **campaigns.schedule** | /campaigns/{campaign_id}/actions/schedule |
| **campaigns.send** | /campaigns/{campaign_id}/actions/send |
| **campaigns.send_test_email** | /campaigns/{campaign_id}/actions/test |
| **campaigns.unschedule** | /campaigns/{campaign_id}/actions/unschedule |
| **campaigns.add_feedback** | /campaigns/{campaign_id}/feedback |
| **campaigns.set_content** | /campaigns/{campaign_id}/content |
| **connectedSites.remove** | /connected-sites/{connected_site_id} |
| **connectedSites.list** | /connected-sites |
| **connectedSites.get** | /connected-sites/{connected_site_id} |
| **connectedSites.create** | /connected-sites |
| **connectedSites.verify_script_installation** | /connected-sites/{connected_site_id}/actions/verify-script-installation |
| **conversations.list** | /conversations |
| **conversations.get** | /conversations/{conversation_id} |
| **conversations.get_conversation_messages** | /conversations/{conversation_id}/messages |
| **conversations.get_conversation_message** | /conversations/{conversation_id}/messages/{message_id} |
| **conversations.create_conversation_message** | /conversations/{conversation_id}/messages |
| **ecommerce.delete_store** | /ecommerce/stores/{store_id} |
| **ecommerce.delete_store_cart** | /ecommerce/stores/{store_id}/carts/{cart_id} |
| **ecommerce.delete_cart_line_item** | /ecommerce/stores/{store_id}/carts/{cart_id}/lines/{line_id} |
| **ecommerce.delete_store_customer** | /ecommerce/stores/{store_id}/customers/{customer_id} |
| **ecommerce.delete_order** | /ecommerce/stores/{store_id}/orders/{order_id} |
| **ecommerce.delete_order_line_item** | /ecommerce/stores/{store_id}/orders/{order_id}/lines/{line_id} |
| **ecommerce.delete_store_product** | /ecommerce/stores/{store_id}/products/{product_id} |
| **ecommerce.delete_product_image** | /ecommerce/stores/{store_id}/products/{product_id}/images/{image_id} |
| **ecommerce.delete_product_variant** | /ecommerce/stores/{store_id}/products/{product_id}/variants/{variant_id} |
| **ecommerce.delete_promo_code** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id}/promo-codes/{promo_code_id} |
| **ecommerce.delete_promo_rule** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id} |
| **ecommerce.orders** | /ecommerce/orders |
| **ecommerce.stores** | /ecommerce/stores |
| **ecommerce.get_store** | /ecommerce/stores/{store_id} |
| **ecommerce.get_store_carts** | /ecommerce/stores/{store_id}/carts |
| **ecommerce.get_store_cart** | /ecommerce/stores/{store_id}/carts/{cart_id} |
| **ecommerce.get_all_cart_line_items** | /ecommerce/stores/{store_id}/carts/{cart_id}/lines |
| **ecommerce.get_cart_line_item** | /ecommerce/stores/{store_id}/carts/{cart_id}/lines/{line_id} |
| **ecommerce.get_all_store_customers** | /ecommerce/stores/{store_id}/customers |
| **ecommerce.get_store_customer** | /ecommerce/stores/{store_id}/customers/{customer_id} |
| **ecommerce.get_store_orders** | /ecommerce/stores/{store_id}/orders |
| **ecommerce.get_order** | /ecommerce/stores/{store_id}/orders/{order_id} |
| **ecommerce.get_all_order_line_items** | /ecommerce/stores/{store_id}/orders/{order_id}/lines |
| **ecommerce.get_order_line_item** | /ecommerce/stores/{store_id}/orders/{order_id}/lines/{line_id} |
| **ecommerce.get_all_store_products** | /ecommerce/stores/{store_id}/products |
| **ecommerce.get_store_product** | /ecommerce/stores/{store_id}/products/{product_id} |
| **ecommerce.get_product_images** | /ecommerce/stores/{store_id}/products/{product_id}/images |
| **ecommerce.get_product_image** | /ecommerce/stores/{store_id}/products/{product_id}/images/{image_id} |
| **ecommerce.get_product_variants** | /ecommerce/stores/{store_id}/products/{product_id}/variants |
| **ecommerce.get_product_variant** | /ecommerce/stores/{store_id}/products/{product_id}/variants/{variant_id} |
| **ecommerce.get_promo_codes** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id}/promo-codes |
| **ecommerce.get_promo_code** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id}/promo-codes/{promo_code_id} |
| **ecommerce.list_promo_rules** | /ecommerce/stores/{store_id}/promo-rules |
| **ecommerce.get_promo_rule** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id} |
| **ecommerce.update_store** | /ecommerce/stores/{store_id} |
| **ecommerce.update_store_cart** | /ecommerce/stores/{store_id}/carts/{cart_id} |
| **ecommerce.update_cart_line_item** | /ecommerce/stores/{store_id}/carts/{cart_id}/lines/{line_id} |
| **ecommerce.update_store_customer** | /ecommerce/stores/{store_id}/customers/{customer_id} |
| **ecommerce.update_order** | /ecommerce/stores/{store_id}/orders/{order_id} |
| **ecommerce.update_order_line_item** | /ecommerce/stores/{store_id}/orders/{order_id}/lines/{line_id} |
| **ecommerce.update_store_product** | /ecommerce/stores/{store_id}/products/{product_id} |
| **ecommerce.update_product_image** | /ecommerce/stores/{store_id}/products/{product_id}/images/{image_id} |
| **ecommerce.update_product_variant** | /ecommerce/stores/{store_id}/products/{product_id}/variants/{variant_id} |
| **ecommerce.update_promo_code** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id}/promo-codes/{promo_code_id} |
| **ecommerce.update_promo_rule** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id} |
| **ecommerce.add_store** | /ecommerce/stores |
| **ecommerce.add_store_cart** | /ecommerce/stores/{store_id}/carts |
| **ecommerce.add_cart_line_item** | /ecommerce/stores/{store_id}/carts/{cart_id}/lines |
| **ecommerce.add_store_customer** | /ecommerce/stores/{store_id}/customers |
| **ecommerce.add_store_order** | /ecommerce/stores/{store_id}/orders |
| **ecommerce.add_order_line_item** | /ecommerce/stores/{store_id}/orders/{order_id}/lines |
| **ecommerce.add_store_product** | /ecommerce/stores/{store_id}/products |
| **ecommerce.add_product_image** | /ecommerce/stores/{store_id}/products/{product_id}/images |
| **ecommerce.add_product_variants** | /ecommerce/stores/{store_id}/products/{product_id}/variants |
| **ecommerce.add_promo_code** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id}/promo-codes |
| **ecommerce.add_promo_rules** | /ecommerce/stores/{store_id}/promo-rules |
| **ecommerce.set_store_customer** | /ecommerce/stores/{store_id}/customers/{customer_id} |
| **ecommerce.add_product_variant** | /ecommerce/stores/{store_id}/products/{product_id}/variants/{variant_id} |
| **facebookAds.list** | /facebook-ads |
| **facebookAds.get_ad** | /facebook-ads/{outreach_id} |
| **fileManager.delete_file** | /file-manager/files/{file_id} |
| **fileManager.delete_folder** | /file-manager/folders/{folder_id} |
| **fileManager.files** | /file-manager/files |
| **fileManager.get_file** | /file-manager/files/{file_id} |
| **fileManager.list_folders** | /file-manager/folders |
| **fileManager.get_folder** | /file-manager/folders/{folder_id} |
| **fileManager.update_file** | /file-manager/files/{file_id} |
| **fileManager.update_folder** | /file-manager/folders/{folder_id} |
| **fileManager.upload** | /file-manager/files |
| **fileManager.create_folder** | /file-manager/folders |
| **landingPages.delete_page** | /landing-pages/{page_id} |
| **landingPages.get_all** | /landing-pages |
| **landingPages.get_page** | /landing-pages/{page_id} |
| **landingPages.get_page_content** | /landing-pages/{page_id}/content |
| **landingPages.update_page** | /landing-pages/{page_id} |
| **landingPages.create** | /landing-pages |
| **landingPages.publish_page** | /landing-pages/{page_id}/actions/publish |
| **landingPages.unpublish_page** | /landing-pages/{page_id}/actions/unpublish |
| **lists.delete_list** | /lists/{list_id} |
| **lists.delete_interest_category** | /lists/{list_id}/interest-categories/{interest_category_id} |
| **lists.delete_interest_category_interest** | /lists/{list_id}/interest-categories/{interest_category_id}/interests/{interest_id} |
| **lists.delete_list_member** | /lists/{list_id}/members/{subscriber_hash} |
| **lists.delete_list_member_note** | /lists/{list_id}/members/{subscriber_hash}/notes/{note_id} |
| **lists.delete_list_merge_field** | /lists/{list_id}/merge-fields/{merge_id} |
| **lists.delete_segment** | /lists/{list_id}/segments/{segment_id} |
| **lists.remove_segment_member** | /lists/{list_id}/segments/{segment_id}/members/{subscriber_hash} |
| **lists.delete_list_webhook** | /lists/{list_id}/webhooks/{webhook_id} |
| **lists.get_list_member_tags** | /lists/{list_id}/members/{subscriber_hash}/tags |
| **lists.get_all_lists** | /lists |
| **lists.get_list** | /lists/{list_id} |
| **lists.get_list_abuse_reports** | /lists/{list_id}/abuse-reports |
| **lists.get_list_abuse_report_details** | /lists/{list_id}/abuse-reports/{report_id} |
| **lists.get_list_recent_activity** | /lists/{list_id}/activity |
| **lists.get_list_clients** | /lists/{list_id}/clients |
| **lists.get_list_growth_history** | /lists/{list_id}/growth-history |
| **lists.get_list_growth_history_by_month** | /lists/{list_id}/growth-history/{month} |
| **lists.get_list_interest_categories** | /lists/{list_id}/interest-categories |
| **lists.get_interest_category** | /lists/{list_id}/interest-categories/{interest_category_id} |
| **lists.list_interest_category_interests** | /lists/{list_id}/interest-categories/{interest_category_id}/interests |
| **lists.get_interest_category_interest** | /lists/{list_id}/interest-categories/{interest_category_id}/interests/{interest_id} |
| **lists.get_list_locations** | /lists/{list_id}/locations |
| **lists.get_list_members_info** | /lists/{list_id}/members |
| **lists.get_list_member** | /lists/{list_id}/members/{subscriber_hash} |
| **lists.get_list_member_activity** | /lists/{list_id}/members/{subscriber_hash}/activity |
| **lists.get_list_member_activity_feed** | /lists/{list_id}/members/{subscriber_hash}/activity-feed |
| **lists.get_list_member_events** | /lists/{list_id}/members/{subscriber_hash}/events |
| **lists.getListMemberGoals** | /lists/{list_id}/members/{subscriber_hash}/goals |
| **lists.get_list_member_notes** | /lists/{list_id}/members/{subscriber_hash}/notes |
| **lists.get_list_member_note** | /lists/{list_id}/members/{subscriber_hash}/notes/{note_id} |
| **lists.get_list_merge_fields** | /lists/{list_id}/merge-fields |
| **lists.get_list_merge_field** | /lists/{list_id}/merge-fields/{merge_id} |
| **lists.get_segment** | /lists/{list_id}/segments/{segment_id} |
| **lists.get_segment_members_list** | /lists/{list_id}/segments/{segment_id}/members |
| **lists.get_list_signup_forms** | /lists/{list_id}/signup-forms |
| **lists.get_list_webhooks** | /lists/{list_id}/webhooks |
| **lists.get_list_webhook** | /lists/{list_id}/webhooks/{webhook_id} |
| **lists.update_list** | /lists/{list_id} |
| **lists.update_interest_category** | /lists/{list_id}/interest-categories/{interest_category_id} |
| **lists.update_interest_category_interest** | /lists/{list_id}/interest-categories/{interest_category_id}/interests/{interest_id} |
| **lists.update_list_member** | /lists/{list_id}/members/{subscriber_hash} |
| **lists.update_list_member_note** | /lists/{list_id}/members/{subscriber_hash}/notes/{note_id} |
| **lists.update_list_merge_field** | /lists/{list_id}/merge-fields/{merge_id} |
| **lists.update_segment** | /lists/{list_id}/segments/{segment_id} |
| **lists.update_list_webhook** | /lists/{list_id}/webhooks/{webhook_id} |
| **lists.create_list_member_event** | /lists/{list_id}/members/{subscriber_hash}/events |
| **lists.update_list_member_tags** | /lists/{list_id}/members/{subscriber_hash}/tags |
| **lists.create_list** | /lists |
| **lists.batch_list_members** | /lists/{list_id} |
| **lists.create_list_interest_category** | /lists/{list_id}/interest-categories |
| **lists.create_interest_category_interest** | /lists/{list_id}/interest-categories/{interest_category_id}/interests |
| **lists.add_list_member** | /lists/{list_id}/members |
| **lists.delete_list_member_permanent** | /lists/{list_id}/members/{subscriber_hash}/actions/delete-permanent |
| **lists.create_list_member_note** | /lists/{list_id}/members/{subscriber_hash}/notes |
| **lists.add_list_merge_field** | /lists/{list_id}/merge-fields |
| **lists.create_segment** | /lists/{list_id}/segments |
| **lists.batch_segment_members** | /lists/{list_id}/segments/{segment_id} |
| **lists.create_segment_member** | /lists/{list_id}/segments/{segment_id}/members |
| **lists.update_list_signup_form** | /lists/{list_id}/signup-forms |
| **lists.create_list_webhook** | /lists/{list_id}/webhooks |
| **lists.list_segments** | /lists/{list_id}/segments |
| **lists.preview_segment** | /lists/{list_id}/preview-segment |
| **lists.set_list_member** | /lists/{list_id}/members/{subscriber_hash} |
| **ping.get** | /ping |
| **reporting.get_facebook_ads_report_all** | /reporting/facebook-ads |
| **reporting.get_facebook_ad_report** | /reporting/facebook-ads/{outreach_id} |
| **reporting.get_facebook_ad_product_activity_report** | /reporting/facebook-ads/{outreach_id}/ecommerce-product-activity |
| **reporting.get_landing_page_reports_all** | /reporting/landing-pages |
| **reporting.get_landing_page_report** | /reporting/landing-pages/{outreach_id} |
| **reports.get_all_campaign_reports** | /reports |
| **reports.get_campaign_report** | /reports/{campaign_id} |
| **reports.get_campaign_abuse_reports** | /reports/{campaign_id}/abuse-reports |
| **reports.get_campaign_abuse_report** | /reports/{campaign_id}/abuse-reports/{report_id} |
| **reports.get_campaign_advice** | /reports/{campaign_id}/advice |
| **reports.get_campaign_click_details** | /reports/{campaign_id}/click-details |
| **reports.get_campaign_click_details_for_link** | /reports/{campaign_id}/click-details/{link_id} |
| **reports.get_subscribers_info** | /reports/{campaign_id}/click-details/{link_id}/members |
| **reports.get_subscriber_info** | /reports/{campaign_id}/click-details/{link_id}/members/{subscriber_hash} |
| **reports.get_domain_performance_for_campaign** | /reports/{campaign_id}/domain-performance |
| **reports.get_ecommerce_product_activity_for_campaign** | /reports/{campaign_id}/ecommerce-product-activity |
| **reports.get_eepurl_activity_for_campaign** | /reports/{campaign_id}/eepurl |
| **reports.get_email_activity_for_campaign** | /reports/{campaign_id}/email-activity |
| **reports.get_email_activity_for_subscriber** | /reports/{campaign_id}/email-activity/{subscriber_hash} |
| **reports.get_locations_for_campaign** | /reports/{campaign_id}/locations |
| **reports.get_campaign_open_details** | /reports/{campaign_id}/open-details |
| **reports.get_subscriber_info_for_opened_campaign** | /reports/{campaign_id}/open-details/{subscriber_hash} |
| **reports.get_campaign_recipients** | /reports/{campaign_id}/sent-to |
| **reports.get_campaign_recipient** | /reports/{campaign_id}/sent-to/{subscriber_hash} |
| **reports.get_sub_reports_for_campaign** | /reports/{campaign_id}/sub-reports |
| **reports.get_unsubscribed_list_for_campaign** | /reports/{campaign_id}/unsubscribed |
| **reports.get_unsubscribed_list_member** | /reports/{campaign_id}/unsubscribed/{subscriber_hash} |
| **root.get_root** | / |
| **searchCampaigns.search** | /search-campaigns |
| **searchMembers.search** | /search-members |
| **templateFolders.remove** | /template-folders/{folder_id} |
| **templateFolders.list** | /template-folders |
| **templateFolders.get** | /template-folders/{folder_id} |
| **templateFolders.update** | /template-folders/{folder_id} |
| **templateFolders.create** | /template-folders |
| **templates.delete_template** | /templates/{template_id} |
| **templates.list** | /templates |
| **templates.get_template** | /templates/{template_id} |
| **templates.get_default_content_for_template** | /templates/{template_id}/default-content |
| **templates.update_template** | /templates/{template_id} |
| **templates.create** | /templates |
| **verifiedDomains.create_verified_domain** | /verified-domains |
| **verifiedDomains.delete_domain** | /verified-domains/{domain_name} |
| **verifiedDomains.get_domain** | /verified-domains/{domain_name} |
| **verifiedDomains.get_verified_domains_all** | /verified-domains |
| **verifiedDomains.submit_domain_verification** | /verified-domains/{domain_name}/actions/verify |


## Additional Libraries

Mailchimp Marketing libraries are available in the following languages:

<div>
  <a href="https://github.com/mailchimp/mailchimp-marketing-node">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_node.png?raw=true" width="44" height="44">
  </a>
  <a href="https://github.com/mailchimp/mailchimp-marketing-php">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_php.png?raw=true" width="44" height="44">
  </a>
  <a href="https://github.com/mailchimp/mailchimp-marketing-ruby">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_ruby.png?raw=true" width="44" height="44">
  </a>
  <a href="https://github.com/mailchimp/mailchimp-marketing-python">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_python.png?raw=true" width="44" height="44">
  </a>
</div>
