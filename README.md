Report Conversations
====

Report Conversations is an add-on for XenForo that allows users to report messages inside conversations. It extends the default reporting functionality.

Installation
----

1. To begin, upload all the files in the *upload/* directory into your XenForo base directory (the one with *library/* and *styles/*).
2. Next, go into your Admin Control Panel, and click *Install Add-on*.
3. Click the *+ Install Add-on* button.
4. Select *addon_ReportConversations.xml* as the file to upload.
5. Click *Install Add-on* to confirm the installation of Report Conversations.
6. Perform the template edits as below.

Template Edits
----

The following template edits must be made to enable XenMoods to work correctly.

- Template: conversation_message

Find:
	<xen:if is="{$message.canEdit}">
		<a href="{xen:link 'conversations/edit-message', $conversation, 'm={$message.message_id}'}"
			class="item control edit"><span></span>{xen:phrase edit}</a>
	</xen:if>

Add Below:
	<a href="{xen:link 'conversations/report', $conversation, 'm={$message.message_id}'}" class="OverlayTrigger item control report" data-cacheOverlay="false"><span></span>{xen:phrase report}</a>

Caveats
----

This add-on has a high probability of being superseded by being introduced into XenForo itself. See the [Report Private Conversation](http://xenforo.com/community/threads/suggestion-report-private-conversation.3912/) thread.

Additionally, no additional permission checks are performed when fetching reports. Any user that can access the *Reported Items* panel will be able to see reported conversations.

Upgrading
----

1. Upload all the Report Conversations files, overwriting any old ones.
2. Next, go to your Admin Control Panel homepage, and click *List Add-ons* or *Manage Add-ons*.
3. Activate the *Controls* drop-down for Report Conversations, and click *Upgrade*.
4. Select *addon_ReportConversations.xml* as the file to upload.
5. Click *Upgrade Add-on* to confirm.
6. Check your template edits to ensure they are up-to-date.

Uninstallation
----

If, for any reason, you would like to uninstall Report Conversations, the following steps are necessary:
1. Undo the template edits that were performed on installation.
2. Go to your Admin Control Panel homepage, and click *List Add-ons* or *Manage Add-ons*.
3. Activate the *Controls* drop-down for Report Conversations, and click *Uninstall*.
4. Remove all the files from XenForo (*library/ReportConversations/*).