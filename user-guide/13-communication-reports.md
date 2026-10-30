# 13. Communication and reports

> **No screenshots for this chapter.** The **Communication** and **Reports** modules are switched **off** for the DoggyVille workspace, and the app returns you to the Dashboard if you open them. This chapter is written from the application's source code. Turn them on in [Settings → Feature flags](14-settings.md#feature-flags).

## Communication (Chat)

**Where (when switched on):** Communication → **Chat** (`/en/t/doggyville/communication`)

A two-pane inbox for talking to customers.

- **Left pane:** the conversation list with a search box (*Search conversations...*). Each row shows the customer, the last message, and how long ago it was sent. Open conversations carry a **New** badge. If there are none, the pane reads *"No conversations found."*
- **Right pane:** the message thread. Your messages sit on the right, the customer's on the left. Opening a conversation marks it as read. Before you pick one, the pane reads *"Select a conversation to start chatting."* An empty thread reads *"No messages yet. Start the conversation!"*
- **Composer:** type in *Type a message...*. **Enter** sends, **Shift+Enter** starts a new line. A paperclip button attaches a file and the arrow sends. If sending fails you see *"Failed to send message."*

This code gave no way to start a new conversation from the staff side; conversations appear when a customer writes.

## Reports

**Where (when switched on):** Reports → **Overview** (`/en/t/doggyville/reports`)

The reports hub shows four headline figures (**Total Revenue, Bookings, Customers, Pets**) and a card for each report category. You only see the categories your role may view; if you can see none, the page says *"No reports available"*.

| Category | What it answers |
|----------|-----------------|
| **Overview** | A snapshot of revenue, bookings, and new customers for the period. |
| **Onboarding** | New customer and pet acquisition trends. |
| **Revenue** | Revenue by source, net of returns. |
| **Inventory** | Stock levels, reorder needs, expiry alerts, supplier spend. |
| **Employee** | Approved hours, days present, completed tasks, revenue contribution. |
| **Bookings & Services** | Which services drive booking volume and revenue. |
| **Memberships & Coupons** | Subscription revenue by plan and coupon use. |

### Filters

- **Date range:** presets **Last 7 days, Last 30 days** (default), **Last 90 days, This month**, or a **custom start and end**.
- Some reports add filters such as booking **status** (Pending, Confirmed, Checked in, In progress, Checked out, Completed, Invoice generated, Payment pending, Closed).

If a report has nothing for the range it shows *"No data to display. No records match the selected date range and filters."*

### Exporting

**Export Reports** lets you choose **From** and **To** dates and download a report as **CSV** or **PDF**. If your browser blocks the pop-up that shows the PDF, allow pop-ups for the site.
