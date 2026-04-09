SOURCE: https://raw.githubusercontent.com/photon-hq/advanced-imessage-kit/main/README.md
SHA256: 5734cf33d1b5c068d83bcb5b878086eaeaa172c8a3ad116a18fb2b86ae857192
BYTES: 45101
---
<div align="center">

![Banner](./.github/assets/banner.png)

# Advanced iMessage Kit

> A powerful TypeScript SDK for iMessage with real-time messaging support

</div>

[![TypeScript](https://img.shields.io/badge/TypeScript-^5-blue.svg)](https://www.typescriptlang.org/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![Discord](https://img.shields.io/badge/Discord-Join-5865F2.svg?logo=discord&logoColor=white)](https://discord.gg/RSJUUHTV)

Advanced iMessage Kit is a full-featured iMessage SDK for **reading**, **sending**, and **automating** iMessage conversations on macOS. Perfect for building **AI agents**, **automation tools**, and **chat applications**.

## Enterprise

**Advanced iMessage Kit** is the **enterprise edition** provided by **[Photon](https://photon.codes)**.

- **Provisioned iMessage Numbers** – Dedicated numbers ready for production use
- **Managed Hosting** – Fully managed infrastructure for reliability and scale  
- **DevOps & Deployment Support** – Production setup, monitoring, and scaling  
- **Enterprise Support** – Direct support and custom integrations  

📩 **Enterprise inquiries:**  
Contact **daniel@photon.codes**

🌐 **Book a Demo:**  
https://photon.codes

If you're looking for the **free/open-source version**, please use **[iMessage Kit](https://github.com/photon-hq/imessage-kit)** instead.


## Features

| Feature                                                    | Description                                   | Method                                       | Example                                                                         |
| ---------------------------------------------------------- | --------------------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------- |
| [Send Messages](#send-messages)                            | Send text messages to any contact             | `messages.sendMessage()`                     | [message-send.ts](./examples/message-send.ts)                                   |
| [Reply to Messages](#send-messages)                        | Reply inline to a specific message            | `messages.sendMessage()`                     | [message-reply.ts](./examples/message-reply.ts)                                 |
| [Message Effects](#send-messages)                          | Send with effects (confetti, fireworks, etc.) | `messages.sendMessage()`                     | [message-effects.ts](./examples/message-effects.ts)                             |
| [Text Styles](#text-styles--animations)                    | Bold, italic, underline, strikethrough        | `messages.sendMessage()`                     | [message-styled.ts](./examples/message-styled.ts)                               |
| [Text Animations](#text-styles--animations)                | Per-character animations (shake, ripple, etc.)| `messages.sendMessage()`                     | [message-styled.ts](./examples/message-styled.ts)                               |
| [Send Rich Links](#send-messages)                          | Send URLs with rich link previews             | `messages.sendMessage()`                     | [message-rich-link.ts](./examples/message-rich-link.ts)                         |
| [Schedule Messages](#scheduled-messages)                   | Send once or on a recurring schedule          | `scheduledMessages.createScheduledMessage()` | [scheduled-message-once.ts](./examples/scheduled-message-once.ts)               |
| [Unsend Messages](#unsend-messages)                        | Retract a sent message                        | `messages.unsendMessage()`                   | [message-unsend.ts](./examples/message-unsend.ts)                               |
| [Edit Messages](#edit-messages)                            | Edit a sent message                           | `messages.editMessage()`                     | [message-edit.ts](./examples/message-edit.ts)                                   |
| [Send Tapbacks](#send-tapbacks)                            | React with ❤️ 👍 👎 😂 ‼️ ❓                  | `messages.sendReaction()`                    | [message-reaction.ts](./examples/message-reaction.ts)                           |
| [Query Messages](#query-messages)                          | Search and filter message history             | `messages.getMessages()`                     | [message-search.ts](./examples/message-search.ts)                               |
| [Destination Caller ID](#query-messages)                   | See which of your addresses sent/received     | `messages.getMessages()`                     | [message-destination-caller-id.ts](./examples/message-destination-caller-id.ts) |
| [Message History](#get-chat-messages)                      | View messages, reactions, polls, stickers     | `chats.getChatMessages()`                    | [message-history.ts](./examples/message-history.ts)                             |
| [Send Attachments](#send-attachments)                      | Send images, files, documents                 | `attachments.sendAttachment()`               | [message-attachment.ts](./examples/message-attachment.ts)                       |
| [Send Audio Messages](#send-audio-messages)                | Send voice messages                           | `attachments.sendAttachment()`               | [message-audio.ts](./examples/message-audio.ts)                                 |
| [Send Stickers](#send-stickers)                            | Send sticker as standalone message            | `attachments.sendSticker()`                  | [message-sticker.ts](./examples/message-sticker.ts)                             |
| [Reply Stickers](#send-stickers)                           | Attach sticker to a message bubble            | `attachments.sendSticker()`                  | [message-reply-sticker.ts](./examples/message-reply-sticker.ts)                 |
| [Download Attachments](#download-attachments)              | Download received files and media             | `attachments.downloadAttachment()`           | [attachment-download.ts](./examples/attachment-download.ts)                     |
| [Get Chats](#get-chats)                                    | List all conversations                        | `chats.getChats()`                           | [chat-fetch.ts](./examples/chat-fetch.ts)                                       |
| [Get Chat Participants](#get-chat-participants)            | View group chat participants                  | `chats.getChat()`                            | [chat-participants.ts](./examples/chat-participants.ts)                         |
| [Manage Group Chats](#manage-group-chats)                  | Add/remove members, rename groups             | `chats.addParticipant()`                     | [chat-group.ts](./examples/chat-group.ts)                                       |
| [Typing Indicators](#typing-indicators)                    | Show "typing..." status                       | `chats.startTyping()`                        | [message-typing.ts](./examples/message-typing.ts)                               |
| [Get Contacts](#get-contacts)                              | Fetch device contacts                         | `contacts.getContacts()`                     | [contact-list.ts](./examples/contact-list.ts)                                   |
| [Share Contact Card](#share-contact-card)                  | Share your contact info in chat               | `contacts.shareContactCard()`                | [message-contact-card.ts](./examples/message-contact-card.ts)                   |
| [Check iMessage Availability](#check-service-availability) | Verify if contact uses iMessage               | `handles.getHandleAvailability()`            | [service-check.ts](./examples/service-check.ts)                                 |
| [Server Info](#get-server-info)                            | Get server status and config                  | `server.getServerInfo()`                     | [server-info.ts](./examples/server-info.ts)                                     |
| [Message Statistics](#message-statistics)                  | Get message counts and analytics              | `server.getMessageStats()`                   | [message-stats.ts](./examples/message-stats.ts)                                 |
| [Create Polls](#create-polls)                              | Create interactive polls in chat              | `polls.create()`                             | [poll-create.ts](./examples/poll-create.ts)                                     |
| [Vote on Polls](#vote-on-polls)                            | Vote or unvote on poll options                | `polls.vote()`                               | [poll-vote.ts](./examples/poll-vote.ts)                                         |
| [Add Poll Options](#add-poll-options)                      | Add options to existing polls                 | `polls.addOption()`                          | [poll-add-option.ts](./examples/poll-add-option.ts)                             |
| [Find My Friends](#find-my-friends)                        | Get friends' locations                        | `icloud.refreshFindMyFriends()`              | [findmy-friends.ts](./examples/findmy-friends.ts)                               |
| [Find My Watch](#find-my-watch)                            | Watch friends' location changes in real-time  | `icloud.refreshFindMyFriends()`              | [findmy-watch.ts](./examples/findmy-watch.ts)                                   |
| [Set Chat Background](#chat-background)                    | Set custom background image for chat          | `chats.setBackground()`                      | [background-set.ts](./examples/background-set.ts)                               |
| [Remove Chat Background](#chat-background)                 | Remove background from chat                   | `chats.removeBackground()`                   | [background-remove.ts](./examples/background-remove.ts)                         |
| [Real-time Events](#real-time-events)                      | Listen for new messages, typing, etc.         | `sdk.on()`                                   | [listen-simple.ts](./examples/listen-simple.ts)                                 |
| [Auto Reply](#real-time-events)                            | Build automated reply bots                    | `sdk.on()`                                   | [auto-reply-hey.ts](./examples/auto-reply-hey.ts)                               |

---

## Quick Start

### Installation

```bash
npm install @photon-ai/advanced-imessage-kit
# or
bun add @photon-ai/advanced-imessage-kit
```

### Basic Usage

```typescript
import { SDK } from "@photon-ai/advanced-imessage-kit";

const sdk = SDK({
  serverUrl: "http://localhost:1234",
});

await sdk.connect();

sdk.on("new-message", (message) => {
  console.log("New message:", message.text);
});

await sdk.messages.sendMessage({
  chatGuid: "iMessage;-;+1234567890",
  message: "Hello World!",
});

await sdk.close();
```

### Configuration

```typescript
interface ClientConfig {
  serverUrl?: string; // Server URL, defaults to "http://localhost:1234"
  apiKey?: string; // API key (if server requires authentication)
  logLevel?: "debug" | "info" | "warn" | "error"; // Log level, defaults to "info"
  logToFile?: boolean; // Enable writing logs to ~/Library/Logs/AdvancedIMessageKit (default true)
}
```

---

## Core Concepts

### chatGuid Format

`chatGuid` is the unique identifier for a conversation. The format is `service;-;address`:

- **iMessage DM**: `iMessage;-;+1234567890` or `iMessage;-;email@example.com`
- **SMS DM**: `SMS;-;+1234567890`
- **Group chat**: `iMessage;+;chat123456789`
- **Auto-detect**: `any;-;+1234567890` (SDK automatically detects the service type)

### How to Get IDs

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  Phone / Email  │────▶│  Build chatGuid │────▶│  Send Message   │
│  +1234567890    │     │ any;-;+123...   │     │  sendMessage()  │
└─────────────────┘     └─────────────────┘     └─────────────────┘

┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   getChats()    │────▶│  Get chat.guid  │────▶│  Use for other  │
│   List chats    │     │                 │     │  operations     │
└─────────────────┘     └─────────────────┘     └─────────────────┘

┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  sendMessage()  │────▶│ Get message.guid│────▶│  edit/unsend    │
│   Send message  │     │                 │     │  sendReaction   │
└─────────────────┘     └─────────────────┘     └─────────────────┘
```

---

## Messages

> Examples: [message-send.ts](./examples/message-send.ts) | [message-unsend.ts](./examples/message-unsend.ts) | [message-edit.ts](./examples/message-edit.ts) | [message-reaction.ts](./examples/message-reaction.ts) | [message-rich-link.ts](./examples/message-rich-link.ts) | [message-search.ts](./examples/message-search.ts)

### Send Messages

```typescript
// Send a text message
const message = await sdk.messages.sendMessage({
  chatGuid: "iMessage;-;+1234567890",
  message: "Hello!",
});

// With subject and effect
await sdk.messages.sendMessage({
  chatGuid: "iMessage;-;+1234567890",
  message: "Happy Birthday!",
  subject: "Wishes",
  effectId: "com.apple.messages.effect.CKConfettiEffect",
});

// Reply to a message
await sdk.messages.sendMessage({
  chatGuid: "iMessage;-;+1234567890",
  message: "This is a reply",
  selectedMessageGuid: "original-message-guid",
});

// Send a rich link preview
await sdk.messages.sendMessage({
  chatGuid: "iMessage;-;+1234567890",
  message: "https://photon.codes/",
  richLink: true,
});
```

**Message Effects**:

| Effect        | effectId                                          |
| ------------- | ------------------------------------------------- |
| Confetti      | `com.apple.messages.effect.CKConfettiEffect`      |
| Fireworks     | `com.apple.messages.effect.CKFireworksEffect`     |
| Balloons      | `com.apple.messages.effect.CKBalloonEffect`       |
| Hearts        | `com.apple.messages.effect.CKHeartEffect`         |
| Lasers        | `com.apple.messages.effect.CKHappyBirthdayEffect` |
| Shooting Star | `com.apple.messages.effect.CKShootingStarEffect`  |
| Sparkles      | `com.apple.messages.effect.CKSparklesEffect`      |
| Echo          | `com.apple.messages.effect.CKEchoEffect`          |
| Spotlight     | `com.apple.messages.effect.CKSpotlightEffect`     |
| Gentle        | `com.apple.MobileSMS.expressivesend.gentle`       |
| Loud          | `com.apple.MobileSMS.expressivesend.loud`         |
| Slam          | `com.apple.MobileSMS.expressivesend.impact`       |
| Invisible Ink | `com.apple.MobileSMS.expressivesend.invisibleink` |

> Example: [message-effects.ts](./examples/message-effects.ts)

### Text Styles & Animations

Apply per-range text formatting and whole-message character animations (requires Private API):

```typescript
// Bold a portion of text
await sdk.messages.sendMessage({
  chatGuid: "iMessage;-;+1234567890",
  message: "This is bold text",
  textStyles: [{ start: 8, end: 12, bold: true }],
});

// Multiple styles in one message
await sdk.messages.sendMessage({
  chatGuid: "iMessage;-;+1234567890",
  message: "Bold here, italic there",
  textStyles: [
    { start: 0, end: 9, bold: true },
    { start: 11, end: 23, italic: true },
  ],
});

// Character animation (applies to whole message)
await sdk.messages.sendMessage({
  chatGuid: "iMessage;-;+1234567890",
  message: "Ripple wave!",
  textAnimation: "ripple",
});

// Combine all three layers
await sdk.messages.sendMessage({
  chatGuid: "iMessage;-;+1234567890",
  message: "Bold shaking fireworks!",
  textStyles: [{ start: 0, end: 4, bold: true }],
  textAnimation: "shake",
  effectId: "com.apple.messages.effect.CKFireworksEffect",
});
```

**Text Style Properties** (per range):

| Property        | Type    | Description    |
| --------------- | ------- | -------------- |
| `start`         | number  | Start index    |
| `end`           | number  | End index      |
| `bold`          | boolean | Bold           |
| `italic`        | boolean | Italic         |
| `underline`     | boolean | Underline      |
| `strikethrough` | boolean | Strikethrough  |

**Text Animations** (whole message):

| `textAnimation` | Description |
| --------------- | ----------- |
| `"big"`         | Big         |
| `"small"`       | Small       |
| `"shake"`       | Shake       |
| `"nod"`         | Nod         |
| `"explode"`     | Explode     |
| `"ripple"`      | Ripple      |
| `"bloom"`       | Bloom       |
| `"jitter"`      | Jitter      |

> Example: [message-styled.ts](./examples/message-styled.ts)

### Query Messages

```typescript
// Get a single message
const message = await sdk.messages.getMessage("message-guid");

// Query messages
const messages = await sdk.messages.getMessages({
  chatGuid: "iMessage;-;+1234567890",
  limit: 50,
  offset: 0,
  sort: "DESC", // DESC = newest first, ASC = oldest first
  before: Date.now(),
  after: Date.now() - 86400000, // Last 24 hours
});

// Search messages
const results = await sdk.messages.searchMessages({
  query: "keyword",
  chatGuid: "iMessage;-;+1234567890", // Optional
  limit: 20,
});

// Get counts
const total = await sdk.messages.getMessageCount();
const sent = await sdk.messages.getSentMessageCount();
const updated = await sdk.messages.getUpdatedMessageCount();
```

### Unsend Messages

```typescript
await sdk.messages.unsendMessage({
  messageGuid: "message-guid-to-unsend",
  partIndex: 0, // Optional
});
```

> Example: [message-unsend.ts](./examples/message-unsend.ts)

### Edit Messages

```typescript
const editedMessage = await sdk.messages.editMessage({
  messageGuid: "message-guid-to-edit",
  editedMessage: "New text content",
  backwardsCompatibilityMessage: "New text content", // Optional, defaults to editedMessage
  partIndex: 0, // Optional, defaults to 0
});

console.log(`Edited: ${editedMessage.guid}`);
console.log(`New text: ${editedMessage.text}`);
console.log(`Date edited: ${editedMessage.dateEdited}`);
```

> Example: [message-edit.ts](./examples/message-edit.ts)

### Send Tapbacks

```typescript
await sdk.messages.sendReaction({
  chatGuid: "iMessage;-;+1234567890",
  messageGuid: "target-message-guid",
  reaction: "love", // love, like, dislike, laugh, emphasize, question
  partIndex: 0, // Optional
});

// Remove a Tapback (prefix with -)
await sdk.messages.sendReaction({
  chatGuid: "iMessage;-;+1234567890",
  messageGuid: "target-message-guid",
  reaction: "-love", // -love, -like, -dislike, -laugh, -emphasize, -question
});
```

> Example: [message-reaction.ts](./examples/message-reaction.ts)

### Other Message Operations

```typescript
// Trigger message notification
await sdk.messages.notifyMessage("message-guid");

// Get embedded media
const media = await sdk.messages.getEmbeddedMedia("message-guid");
```

---

## Scheduled Messages

> Examples: [scheduled-message-once.ts](./examples/scheduled-message-once.ts) | [scheduled-message-recurring.ts](./examples/scheduled-message-recurring.ts) | [scheduled-message-manage.ts](./examples/scheduled-message-manage.ts)

### Schedule a one-time message

```typescript
const scheduled = await sdk.scheduledMessages.createScheduledMessage({
  type: "send-message",
  payload: {
    chatGuid: "any;-;+1234567890",
    message: "This is a scheduled message!",
    method: "apple-script",
  },
  scheduledFor: Date.now() + 3 * 1000,
  schedule: { type: "once" },
});
```

### Schedule a recurring message

```typescript
const tomorrow9am = new Date();
tomorrow9am.setDate(tomorrow9am.getDate() + 1);
tomorrow9am.setHours(9, 0, 0, 0);

const daily = await sdk.scheduledMessages.createScheduledMessage({
  type: "send-message",
  payload: {
    chatGuid: "any;-;+1234567890",
    message: "Good morning!",
    method: "apple-script",
  },
  scheduledFor: tomorrow9am.getTime(),
  schedule: {
    type: "recurring",
    intervalType: "daily", // hourly, daily, weekly, monthly, yearly
    interval: 1,
  },
});
```

### Manage scheduled messages

```typescript
const scheduledMessages = await sdk.scheduledMessages.getScheduledMessages();

const updated = await sdk.scheduledMessages.updateScheduledMessage(
  "scheduled-id",
  {
    type: "send-message",
    payload: {
      chatGuid: "any;-;+1234567890",
      message: "Updated message!",
      method: "apple-script",
    },
    scheduledFor: Date.now() + 10 * 60 * 1000,
    schedule: { type: "once" },
  },
);

await sdk.scheduledMessages.deleteScheduledMessage("scheduled-id");
```

---

## Chats

> Examples: [chat-fetch.ts](./examples/chat-fetch.ts) | [chat-group.ts](./examples/chat-group.ts) | [message-typing.ts](./examples/message-typing.ts) | [background-set.ts](./examples/background-set.ts) | [background-remove.ts](./examples/background-remove.ts)

### Get Chats

```typescript
const chats = await sdk.chats.getChats({
  withLastMessage: true, // Include last message
  withArchived: false, // Include archived chats
  offset: 0,
  limit: 50,
});

// Get chat count
const count = await sdk.chats.getChatCount();
```

### Get Single Chat

```typescript
const chat = await sdk.chats.getChat("chat-guid", {
  with: ["participants", "lastMessage"],
});
```

### Get Chat Participants

Get participants from group chats and display them with contact names:

```typescript
const chats = await sdk.chats.getChats();
const groups = chats.filter((chat) => chat.style === 43); // Filter group chats

// Get contacts for name mapping
const contacts = await sdk.contacts.getContacts();
const nameMap = new Map<string, string>();
for (const c of contacts) {
  const name = c.displayName || c.firstName || "";
  if (!name) continue;
  for (const p of c.phoneNumbers || []) nameMap.set(p.address, name);
  for (const e of c.emails || []) nameMap.set(e.address, name);
}

// Display participants
groups.forEach((group) => {
  console.log(`Group: ${group.displayName || group.chatIdentifier}`);
  group.participants?.forEach((p) => {
    const name = nameMap.get(p.address);
    const display = name ? `${name} <${p.address}>` : p.address;
    console.log(`  - ${display} (${p.service})`);
  });
});
```

> Example: [chat-participants.ts](./examples/chat-participants.ts)

### Create Chat

```typescript
const newChat = await sdk.chats.createChat({
  addresses: ["+1234567890", "+0987654321"],
  message: "Hello everyone!", // Optional initial message
  service: "iMessage", // "iMessage" or "SMS"
  method: "private-api", // "apple-script" or "private-api"
});
```

### Chat Status

```typescript
// Mark as read/unread
await sdk.chats.markChatRead("chat-guid");
await sdk.chats.markChatUnread("chat-guid");

// Delete chat
await sdk.chats.deleteChat("chat-guid");
```

### Typing Indicators

```typescript
// Show "typing..."
await sdk.chats.startTyping("chat-guid");

// Stop showing
await sdk.chats.stopTyping("chat-guid");
```

> Example: [message-typing.ts](./examples/message-typing.ts)

### Get Chat Messages

```typescript
const messages = await sdk.chats.getChatMessages("chat-guid", {
  limit: 100,
  offset: 0,
  sort: "DESC",
  before: Date.now(),
  after: Date.now() - 86400000,
});
```

### Manage Group Chats

```typescript
// Rename group
await sdk.chats.updateChat("chat-guid", {
  displayName: "New Group Name",
});

// Add participant
await sdk.chats.addParticipant("chat-guid", "+1234567890");

// Remove participant
await sdk.chats.removeParticipant("chat-guid", "+1234567890");

// Leave group
await sdk.chats.leaveChat("chat-guid");
```

### Group Icon

```typescript
// Set group icon
await sdk.chats.setGroupIcon("chat-guid", "/path/to/image.jpg");

// Get group icon
const iconBuffer = await sdk.chats.getGroupIcon("chat-guid");

// Remove group icon
await sdk.chats.removeGroupIcon("chat-guid");
```

> Example: [chat-group.ts](./examples/chat-group.ts)

### Chat Background

Set, get, or remove custom background images for individual chats:

```typescript
// Get current background info
const bgInfo = await sdk.chats.getBackground("chat-guid");
console.log(`Has background: ${bgInfo.hasBackground}`);
if (bgInfo.hasBackground) {
  console.log(`Background ID: ${bgInfo.backgroundId}`);
  console.log(`Image URL: ${bgInfo.imageUrl}`);
}

// Set a background image (using file path)
await sdk.chats.setBackground("chat-guid", {
  filePath: "/path/to/image.png",
});

// Set a background image (using base64)
import fs from "node:fs";
const imageBuffer = fs.readFileSync("/path/to/image.png");
await sdk.chats.setBackground("chat-guid", {
  fileData: imageBuffer.toString("base64"),
});

// Remove background
await sdk.chats.removeBackground("chat-guid");
```

> Examples: [background-set.ts](./examples/background-set.ts) | [background-remove.ts](./examples/background-remove.ts)

---

## Attachments

> Examples: [message-attachment.ts](./examples/message-attachment.ts) | [message-audio.ts](./examples/message-audio.ts) | [message-reply-sticker.ts](./examples/message-reply-sticker.ts) | [attachment-download.ts](./examples/attachment-download.ts)

### Send Attachments

```typescript
const message = await sdk.attachments.sendAttachment({
  chatGuid: "iMessage;-;+1234567890",
  filePath: "/path/to/file.jpg",
  fileName: "custom-name.jpg", // Optional
});
```

### Send Audio Messages

```typescript
const message = await sdk.attachments.sendAttachment({
  chatGuid: "iMessage;-;+1234567890",
  filePath: "/path/to/audio.m4a",
  isAudioMessage: true,
});
```

> Example: [message-audio.ts](./examples/message-audio.ts)

### Send Stickers

Stickers can be sent in two ways:

**Standalone Sticker** - Sends as its own message (like sending an image, but with sticker styling):

```typescript
await sdk.attachments.sendSticker({
  chatGuid: "iMessage;-;+1234567890",
  filePath: "/path/to/sticker.png",
});
```

> Example: [message-sticker.ts](./examples/message-sticker.ts)

**Reply Sticker (Tapback Sticker)** - Attaches to an existing message bubble:

```typescript
await sdk.attachments.sendSticker({
  chatGuid: "iMessage;-;+1234567890",
  filePath: "/path/to/sticker.png",
  selectedMessageGuid: "target-message-guid", // Required for reply sticker
  stickerX: 0.5, // Position X (0-1), default: 0.5
  stickerY: 0.5, // Position Y (0-1), default: 0.5
  stickerScale: 0.75, // Scale (0-1), default: 0.75
  stickerRotation: 0, // Rotation in radians, default: 0
  stickerWidth: 300, // Width in pixels, default: 300
});
```

> Example: [message-reply-sticker.ts](./examples/message-reply-sticker.ts)

### Get Attachment Info

```typescript
// Get attachment details
const attachment = await sdk.attachments.getAttachment("attachment-guid");

// Get total count
const count = await sdk.attachments.getAttachmentCount();
```

### Download Attachments

```typescript
// Download attachment
const buffer = await sdk.attachments.downloadAttachment("attachment-guid", {
  original: true, // Download original file
  force: false, // Force re-download
  width: 800, // Image width (for thumbnails)
  height: 600, // Image height
  quality: 80, // Image quality
});

// Download Live Photo video
const liveBuffer =
  await sdk.attachments.downloadAttachmentLive("attachment-guid");

// Get blurhash (for placeholders)
const blurhash = await sdk.attachments.getAttachmentBlurhash("attachment-guid");
```

> Example: [attachment-download.ts](./examples/attachment-download.ts)

---

## Contacts

> Example: [contact-list.ts](./examples/contact-list.ts)

### Get Contacts

```typescript
const contacts = await sdk.contacts.getContacts();
```

### Get Contact Card

```typescript
// Get contact card by phone or email
const card = await sdk.contacts.getContactCard("+1234567890");
// {
//   firstName: "John",
//   lastName: "Doe",
//   emails: ["john@example.com"],
//   phones: ["+1234567890"],
//   ...
// }
```

### Share Contact Card

Share your contact card with a chat:

```typescript
// chatGuid is the chat identifier (e.g. the `guid` field you get from chat APIs/events)
// Check whether the SDK recommends sharing your contact card in this chat.
//
// Returns:
// - true: sharing is recommended (typically when the other side shared theirs and you haven't shared yours yet)
// - false: NOT recommended (e.g. you've already shared, OR the other side hasn't shared theirs yet)
const shouldShare = await sdk.contacts.shouldShareContact("chat-guid");

if (shouldShare) {
  // Share your contact card (iMessage "Share Name and Photo")
  await sdk.contacts.shareContactCard("chat-guid");
}
```

> Example: [message-contact-card.ts](./examples/message-contact-card.ts)

---

## Handles

> Examples: [service-check.ts](./examples/service-check.ts) | [handle-query.ts](./examples/handle-query.ts)

A Handle represents a messaging address (phone number or email).

### Query Handles

```typescript
// Query handles
const result = await sdk.handles.queryHandles({
  address: "+1234567890", // Optional, filter by address
  with: ["chats"], // Optional, include related chats
  offset: 0,
  limit: 50,
});

// Get single handle
const handle = await sdk.handles.getHandle("handle-guid");

// Get total count
const count = await sdk.handles.getHandleCount();
```

### Check Service Availability

Check if a phone/email supports iMessage or FaceTime:

```typescript
// First parameter is the address (phone or email), not handle guid
const hasIMessage = await sdk.handles.getHandleAvailability(
  "+1234567890",
  "imessage",
);
const hasFaceTime = await sdk.handles.getHandleAvailability(
  "+1234567890",
  "facetime",
);

// Choose service based on availability
const chatGuid = hasIMessage ? `iMessage;-;+1234567890` : `SMS;-;+1234567890`;
```

> Example: [service-check.ts](./examples/service-check.ts)

### Get Focus Status

```typescript
const focusStatus = await sdk.handles.getHandleFocusStatus("handle-guid");
```

---

## Server

> Examples: [message-stats.ts](./examples/message-stats.ts) | [server-info.ts](./examples/server-info.ts)

### Get Server Info

```typescript
const info = await sdk.server.getServerInfo();
// {
//   os_version: "14.0",
//   server_version: "1.0.0",
//   private_api: true,
//   helper_connected: true,
//   detected_icloud: "user@icloud.com",
//   ...
// }
```

### Message Statistics

```typescript
const stats = await sdk.server.getMessageStats();
// {
//   total: 12345,
//   sent: 5000,
//   received: 7345,
//   last24h: 50,
//   last7d: 300,
//   last30d: 1000,
// }
```

### Media Statistics

```typescript
// All media stats
const mediaStats = await sdk.server.getMediaStatistics();

// Per-chat media stats
const chatMediaStats = await sdk.server.getMediaStatisticsByChat();
```

### Server Logs

```typescript
const logs = await sdk.server.getServerLogs(100); // Get last 100 logs
```

---

## Polls

> Examples: [poll-create.ts](./examples/poll-create.ts) | [poll-vote.ts](./examples/poll-vote.ts) | [poll-unvote.ts](./examples/poll-unvote.ts) | [poll-add-option.ts](./examples/poll-add-option.ts)

### Create Polls

```typescript
const pollMessage = await sdk.polls.create({
  chatGuid: "iMessage;-;+1234567890",
  title: "What should we do?", // Optional
  options: ["Option A", "Option B", "Option C"],
});

console.log("Poll GUID:", pollMessage.guid);
```

> Example: [poll-create.ts](./examples/poll-create.ts)

### Add Poll Options

```typescript
await sdk.polls.addOption({
  chatGuid: "iMessage;-;+1234567890",
  pollMessageGuid: "poll-message-guid",
  optionText: "New Option D",
});
```

> Example: [poll-add-option.ts](./examples/poll-add-option.ts)

### Vote on Polls

```typescript
// Vote on a poll option
await sdk.polls.vote({
  chatGuid: "iMessage;-;+1234567890",
  pollMessageGuid: "poll-message-guid",
  optionIdentifier: "option-uuid", // UUID of the option to vote for
});

// Remove your vote
await sdk.polls.unvote({
  chatGuid: "iMessage;-;+1234567890",
  pollMessageGuid: "poll-message-guid",
  optionIdentifier: "option-uuid",
});
```

> Examples: [poll-vote.ts](./examples/poll-vote.ts) | [poll-unvote.ts](./examples/poll-unvote.ts)

### Parse Poll Messages

Use the `poll-utils` helper functions to parse and display poll messages:

```typescript
import {
  isPollMessage,
  isPollVote,
  parsePollDefinition,
  parsePollVotes,
  getPollSummary,
  getOptionTextById,
} from "@photon-ai/advanced-imessage-kit";

sdk.on("new-message", (message) => {
  if (isPollMessage(message)) {
    if (isPollVote(message)) {
      // Parse vote data
      const voteData = parsePollVotes(message);
      console.log("Votes:", voteData?.votes);

      // Get option text for each vote
      voteData?.votes.forEach((vote) => {
        const optionText = getOptionTextById(vote.voteOptionIdentifier);
        console.log(`${vote.participantHandle} voted for "${optionText}"`);
      });
    } else {
      // Parse poll definition
      const pollData = parsePollDefinition(message);
      console.log("Poll title:", pollData?.title);
      console.log("Options:", pollData?.options);
    }

    // Or get a formatted summary
    console.log(getPollSummary(message));
  }
});
```

**Note**: Poll definitions are automatically cached when received. When a vote arrives, the SDK looks up the corresponding option text from the cache. If you receive a vote for a poll that was created before the SDK started, the option text won't be available and will show the UUID instead.

---

## iCloud

> Examples: [findmy-friends.ts](./examples/findmy-friends.ts) | [findmy-watch.ts](./examples/findmy-watch.ts)

### Find My Friends

```typescript
// Refresh and get friends' locations
const locations = await sdk.icloud.refreshFindMyFriends();

// Each location contains:
// - handle: phone number or email
// - coordinates: [latitude, longitude]
// - long_address: street address (optional)
// - expiry: timestamp when location expires (optional)

// Find specific friend
const friend = locations.find((loc) => loc.handle === "+1234567890");
if (friend) {
  console.log(
    `Coordinates: ${friend.coordinates[0]}, ${friend.coordinates[1]}`,
  );
  console.log(
    `Maps: https://maps.google.com/?q=${friend.coordinates[0]},${friend.coordinates[1]}`,
  );
  if (friend.long_address) console.log(`Address: ${friend.long_address}`);
}

// List all friends
console.log(`All Friends (${locations.length}):`);
for (const loc of locations) {
  console.log(`${loc.handle}: ${loc.coordinates[0]}, ${loc.coordinates[1]}`);
}
```

> Example: [findmy-friends.ts](./examples/findmy-friends.ts)

### Find My Watch

Watch friends' location changes in real-time. Fetches initial locations on connect, then listens for live updates via the `new-findmy-location` event (server auto-refreshes every 30s):

```typescript
import type { FindMyLocationItem } from "@photon-ai/advanced-imessage-kit";

// Fetch initial locations on ready
sdk.on("ready", async () => {
  const locations = await sdk.icloud.refreshFindMyFriends();
  for (const loc of locations) {
    console.log(`${loc.handle}`);
    console.log(`  Coordinates: ${loc.coordinates[0]}, ${loc.coordinates[1]}`);
    console.log(
      `  Maps: https://maps.google.com/?q=${loc.coordinates[0]},${loc.coordinates[1]}`,
    );
    if (loc.long_address) console.log(`  Address: ${loc.long_address}`);
  }
});

// Listen for real-time location updates
sdk.on("new-findmy-location", (location: FindMyLocationItem) => {
  console.log(`${location.handle} updated:`);
  console.log(
    `  Coordinates: ${location.coordinates[0]}, ${location.coordinates[1]}`,
  );
});
```

> Example: [findmy-watch.ts](./examples/findmy-watch.ts)

---

## Real-time Events

> Examples: [listen-simple.ts](./examples/listen-simple.ts) | [listen-advanced.ts](./examples/listen-advanced.ts) | [auto-reply-hey.ts](./examples/auto-reply-hey.ts)

The SDK receives real-time events from the server via Socket.IO.

### Connection Events

```typescript
sdk.on("ready", () => {
  console.log("SDK connected and ready");
});

sdk.on("disconnect", () => {
  console.log("Disconnected");
});

sdk.on("error", (error) => {
  console.error("Error:", error);
});
```

### Message Events

```typescript
// New message
sdk.on("new-message", (message) => {
  console.log("New message:", message.text);
  console.log("From:", message.handle?.address);
  console.log("From me:", message.isFromMe);
});

// Message status update (delivered, read, etc.)
sdk.on("updated-message", (message) => {
  if (message.dateRead) console.log("Message read");
  else if (message.dateDelivered) console.log("Message delivered");
});

// Send failed
sdk.on("message-send-error", (data) => {
  console.error("Send failed:", data);
});
```

### Chat Events

```typescript
// Chat read status changed
sdk.on("chat-read-status-changed", ({ chatGuid, read }) => {
  console.log(`Chat ${chatGuid} marked as ${read ? "read" : "unread"}`);
});
```

### Typing Indicators

```typescript
sdk.on("typing-indicator", ({ display, guid }) => {
  console.log(`${guid} ${display ? "is typing" : "stopped typing"}`);
});
```

### Group Events

```typescript
sdk.on("group-name-change", (message) => {
  console.log("Group renamed to:", message.groupTitle);
});

sdk.on("participant-added", (message) => {
  console.log("Someone joined the group");
});

sdk.on("participant-removed", (message) => {
  console.log("Someone was removed from the group");
});

sdk.on("participant-left", (message) => {
  console.log("Someone left the group");
});

sdk.on("group-icon-changed", (message) => {
  console.log("Group icon changed");
});

sdk.on("group-icon-removed", (message) => {
  console.log("Group icon removed");
});
```

### Find My Friends Events

```typescript
sdk.on("new-findmy-location", (location) => {
  console.log(`${location.handle} location updated:`, location.coordinates);
});
```

### Remove Event Listeners

```typescript
const handler = (message) => console.log(message);
sdk.on("new-message", handler);

// Remove specific listener
sdk.off("new-message", handler);

// Remove all listeners
sdk.removeAllListeners("new-message");
```

---

## Best Practices

### Resource Management

```typescript
// Graceful shutdown
process.on("SIGINT", async () => {
  await sdk.close();
  process.exit(0);
});
```

### Message Deduplication

The SDK includes built-in message deduplication to prevent processing duplicates during network instability:

```typescript
// Clear processed messages (prevent memory leaks)
sdk.clearProcessedMessages(1000);

// Get processed message count
const count = sdk.getProcessedMessageCount();
```

### Error Handling

```typescript
try {
  await sdk.messages.sendMessage({
    chatGuid: "invalid-guid",
    message: "test",
  });
} catch (error) {
  if (error.response?.status === 404) {
    console.error("Chat not found");
  } else {
    console.error("Send failed:", error.message);
  }
}
```

### Auto-create Chats

When sending to a contact you've never messaged before, the SDK automatically creates the chat:

```typescript
// Works even without existing chat history
await sdk.messages.sendMessage({
  chatGuid: "any;-;+1234567890",
  message: "Hi, this is John",
});
// SDK detects the chat doesn't exist, creates it, then sends
```

---

## Examples

Run any example with Bun:

```bash
bun run examples/<filename>.ts
```

### Getting Started

| File                                                      | Description                            |
| --------------------------------------------------------- | -------------------------------------- |
| [listen-simple.ts](./examples/listen-simple.ts)           | Listen with formatted output           |
| [listen-advanced.ts](./examples/listen-advanced.ts)       | Listen with full JSON and startup info |
| [message-send.ts](./examples/message-send.ts)             | Send text messages                     |
| [message-attachment.ts](./examples/message-attachment.ts) | Send attachments                       |
| [message-audio.ts](./examples/message-audio.ts)           | Send audio messages                    |

### Message Operations

| File                                                                            | Description           |
| ------------------------------------------------------------------------------- | --------------------- |
| [message-reply.ts](./examples/message-reply.ts)                                 | Reply to messages     |
| [message-unsend.ts](./examples/message-unsend.ts)                               | Unsend messages       |
| [message-edit.ts](./examples/message-edit.ts)                                   | Edit messages         |
| [message-reaction.ts](./examples/message-reaction.ts)                           | Send Tapbacks         |
| [message-effects.ts](./examples/message-effects.ts)                             | Message effects          |
| [message-styled.ts](./examples/message-styled.ts)                               | Text styles & animations |
| [message-search.ts](./examples/message-search.ts)                               | Search messages          |
| [message-history.ts](./examples/message-history.ts)                             | Message history       |
| [message-destination-caller-id.ts](./examples/message-destination-caller-id.ts) | Destination caller ID |

### Chats & Groups

| File                                                    | Description            |
| ------------------------------------------------------- | ---------------------- |
| [chat-fetch.ts](./examples/chat-fetch.ts)               | Get chat list          |
| [chat-participants.ts](./examples/chat-participants.ts) | Get group participants |
| [chat-group.ts](./examples/chat-group.ts)               | Manage groups          |
| [message-typing.ts](./examples/message-typing.ts)       | Typing indicators      |
| [background-set.ts](./examples/background-set.ts)       | Set chat background    |
| [background-remove.ts](./examples/background-remove.ts) | Remove chat background |

### Contacts & Services

| File                                                            | Description                   |
| --------------------------------------------------------------- | ----------------------------- |
| [contact-list.ts](./examples/contact-list.ts)                   | Get contacts                  |
| [message-contact-card.ts](./examples/message-contact-card.ts)   | Share contact card            |
| [service-check.ts](./examples/service-check.ts)                 | Check iMessage availability   |
| [message-service-check.ts](./examples/message-service-check.ts) | Monitor message service types |

### Attachments & Media

| File                                                            | Description              |
| --------------------------------------------------------------- | ------------------------ |
| [attachment-download.ts](./examples/attachment-download.ts)     | Download attachments     |
| [message-sticker.ts](./examples/message-sticker.ts)             | Send standalone stickers |
| [message-reply-sticker.ts](./examples/message-reply-sticker.ts) | Send reply stickers      |

### Polls

| File                                                | Description      |
| --------------------------------------------------- | ---------------- |
| [poll-create.ts](./examples/poll-create.ts)         | Create polls     |
| [poll-vote.ts](./examples/poll-vote.ts)             | Vote on polls    |
| [poll-unvote.ts](./examples/poll-unvote.ts)         | Unvote on polls  |
| [poll-add-option.ts](./examples/poll-add-option.ts) | Add poll options |

### Server & Advanced

| File                                              | Description          |
| ------------------------------------------------- | -------------------- |
| [server-info.ts](./examples/server-info.ts)       | Server info and logs |
| [message-stats.ts](./examples/message-stats.ts)   | Message statistics   |
| [findmy-friends.ts](./examples/findmy-friends.ts) | Find My Friends      |
| [findmy-watch.ts](./examples/findmy-watch.ts)     | Find My Watch        |
| [auto-reply-hey.ts](./examples/auto-reply-hey.ts) | Auto reply bot       |

---

## LLMs

Download `llms.txt` for language model context:

- [Download llms.txt](./llms.txt)

---

## License

MIT License

## Author

[@Artist-MOBAI](https://github.com/Artist-MOBAI)


SOURCE: https://raw.githubusercontent.com/photon-hq/imessage-kit/main/README.md
SHA256: 66fc450472cecfc03a3a6af5ab16e7f9a7e655a3000571851805e7c7398704c3
BYTES: 15354
---
<div align="center">
  
![Banner](./.github/assets/banner.png)

# @photon-ai/imessage-kit

> A type-safe, elegant iMessage SDK for macOS with cross-runtime support

</div>

[![npm version](https://img.shields.io/npm/v/@photon-ai/imessage-kit.svg)](https://www.npmjs.com/package/@photon-ai/imessage-kit)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.3-blue.svg)](https://www.typescriptlang.org/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![Discord](https://img.shields.io/badge/Discord-Join-5865F2.svg?logo=discord&logoColor=white)](https://discord.gg/bZd4CMd2H5)

A full-featured iMessage SDK for **reading**, **sending**, and **automating** iMessage conversations on macOS. Perfect for building AI agents, automation tools, and chat-first applications.

> [!NOTE]
> **✨ Looking for advanced features like threaded replies, tapbacks, message editing, unsending, live typing indicators? Check out [Advanced iMessage Kit](https://github.com/photon-hq/advanced-imessage-kit) and contact us at daniel@photon.codes.**

---

## Features

| Feature | Method | Example |
|---------|--------|---------|
| [Send Messages](#send-messages) | `sdk.send()` | [01-send-text.ts](./examples/01-send-text.ts) |
| [Send Images](#send-images) | `sdk.send()` | [02-send-image.ts](./examples/02-send-image.ts) |
| [Send Files](#send-files) | `sdk.sendFile()` | [03-send-file.ts](./examples/03-send-file.ts) |
| [Send to Groups](#send-to-groups) | `sdk.send()` | [04-send-group.ts](./examples/04-send-group.ts) |
| [Query Messages](#query-messages) | `sdk.getMessages()` | [05-query-messages.ts](./examples/05-query-messages.ts) |
| [List Chats](#list-chats) | `sdk.listChats()` | [06-list-chats.ts](./examples/06-list-chats.ts) |
| [Real-time Watching](#real-time-watching) | `sdk.startWatching()` | [07-watch-messages.ts](./examples/07-watch-messages.ts) |
| [Auto Reply](#auto-reply) | `sdk.message()` | [08-auto-reply.ts](./examples/08-auto-reply.ts) |
| Batch Send | `sdk.sendBatch()` | [09-batch-send.ts](./examples/09-batch-send.ts) |
| Get Sent Message | `sdk.send()` | [10-get-sent-message.ts](./examples/10-get-sent-message.ts) |
| [Plugin System](#plugin-system) | `sdk.use()` | [11-plugin.ts](./examples/11-plugin.ts) |
| [Error Handling](#error-handling) | `SendError` | [12-error-handling.ts](./examples/12-error-handling.ts) |
| Watch Own Messages | `sdk.startWatching()` | [13-watch-own-messages.ts](./examples/13-watch-own-messages.ts) |
| [Scheduled Messages](#scheduled-messages) | `MessageScheduler` | [14-scheduled-messages.ts](./examples/14-scheduled-messages.ts) |
| [Smart Reminders](#smart-reminders) | `Reminders` | [15-smart-reminders.ts](./examples/15-smart-reminders.ts) |

---

## Quick Start

### Installation

```bash
# For Bun (zero dependencies)
bun add @photon-ai/imessage-kit

# For Node.js (requires better-sqlite3)
npm install @photon-ai/imessage-kit better-sqlite3
```

### Basic Usage

```typescript
import { IMessageSDK } from '@photon-ai/imessage-kit'

const sdk = new IMessageSDK()

// Send a message
await sdk.send('+1234567890', 'Hello from iMessage Kit!')

// Clean up
await sdk.close()
```

### Configuration

```typescript
interface IMessageConfig {
    debug?: boolean              // Enable debug logging
    maxConcurrent?: number       // Max concurrent sends (default: 5)
    scriptTimeout?: number       // AppleScript timeout in ms
    databasePath?: string        // Custom database path
    plugins?: Plugin[]           // Plugins
    watcher?: {
        pollInterval?: number    // Polling interval (default: 2000)
        unreadOnly?: boolean     // Only watch unread (default: false)
        excludeOwnMessages?: boolean  // Exclude own messages (default: true)
    }
    webhook?: {
        url: string
        headers?: Record<string, string>
    }
}
```

### Granting Permission

`IMessageKit` requires **Full Disk Access** to read your chat history and perform automation tasks.

1. Open **System Settings → Privacy & Security → Full Disk Access**
2. Click **"+"** and add your IDE or terminal (e.g., Cursor, VS Code, Terminal, Warp)

---

## Messages

> Examples: [01-send-text.ts](./examples/01-send-text.ts) | [02-send-image.ts](./examples/02-send-image.ts) | [03-send-file.ts](./examples/03-send-file.ts) | [05-query-messages.ts](./examples/05-query-messages.ts)

### Send Messages

```typescript
// Send text
await sdk.send('+1234567890', 'Hello World!')

// Send to email
await sdk.send('user@example.com', 'Hello!')
```

### Send Images

```typescript
// Send local images
await sdk.send('+1234567890', { 
    images: ['image1.jpg', 'image2.png'] 
})

// Send network images (auto-download)
await sdk.send('+1234567890', { 
    images: ['https://example.com/image.jpg'] 
})

// Text with images
await sdk.send('+1234567890', { 
    text: 'Check this out!',
    images: ['photo.jpg']
})
```

### Send Files

```typescript
// Send files (PDF, CSV, VCF, etc.)
await sdk.send('+1234567890', { 
    files: ['document.pdf', 'data.csv', 'contact.vcf'] 
})

// Convenience methods
await sdk.sendFile('+1234567890', '/path/to/document.pdf')
await sdk.sendFiles('+1234567890', ['file1.pdf', 'file2.csv'], 'Multiple files')
```

### Query Messages

```typescript
// Get messages with filters
const result = await sdk.getMessages({
    sender: '+1234567890',
    unreadOnly: true,
    limit: 20,
    since: new Date('2025-01-01'),
    search: 'meeting'
})

// Get unread messages grouped by sender
const unread = await sdk.getUnreadMessages()
console.log(`${unread.total} unread from ${unread.senderCount} senders`)
```

---

## Chats

> Examples: [04-send-group.ts](./examples/04-send-group.ts) | [06-list-chats.ts](./examples/06-list-chats.ts)

### List Chats

```typescript
// Get all chats
const all = await sdk.listChats()

// Filter chats
const groups = await sdk.listChats({
    type: 'group',
    hasUnread: true,
    sortBy: 'recent',
    search: 'Project',
    limit: 20
})

// Each chat includes
for (const chat of groups) {
    console.log({
        chatId: chat.chatId,
        name: chat.displayName,
        isGroup: chat.isGroup,
        unread: chat.unreadCount
    })
}
```

### Send to Groups

```typescript
// Get group chatId from listChats()
const groups = await sdk.listChats({ type: 'group' })
const chatId = groups[0].chatId  // e.g., 'chat45e2b868...'

// Send to group
await sdk.send(chatId, 'Hello group!')
await sdk.send(chatId, {
    text: 'Check these files',
    files: ['report.pdf']
})
```

---

## Real-time Events

> Examples: [07-watch-messages.ts](./examples/07-watch-messages.ts) | [08-auto-reply.ts](./examples/08-auto-reply.ts) | [13-watch-own-messages.ts](./examples/13-watch-own-messages.ts)

### Real-time Watching

```typescript
await sdk.startWatching({
    // All messages
    onMessage: (msg) => {
        console.log(`New: ${msg.text}`)
    },
    
    // DMs only
    onDirectMessage: (msg) => {
        console.log(`DM from ${msg.sender}`)
    },
    
    // Groups only
    onGroupMessage: (msg) => {
        console.log(`Group: ${msg.chatId}`)
    },
    
    onError: (error) => {
        console.error(error)
    }
})

// Stop watching
sdk.stopWatching()
```

### Auto Reply

```typescript
await sdk.startWatching({
    onDirectMessage: async (msg) => {
        await sdk.message(msg)
            .ifFromOthers()
            .matchText(/hello/i)
            .replyText('Hi there!')
            .execute()
    }
})
```

### Message Chain API

```typescript
await sdk.message(msg)
    .ifUnread()
    .ifNotReaction()   // Skip tapback reactions
    .ifGroupChat()
    .when(m => m.sender.startsWith('+1'))
    .matchText(/photo/i)
    .replyImage(['photo.jpg'])
    .execute()
```

---

## Attachments

> Examples: [02-send-image.ts](./examples/02-send-image.ts) | [03-send-file.ts](./examples/03-send-file.ts)

### Attachment Helpers

```typescript
import {
    attachmentExists,
    downloadAttachment,
    getAttachmentSize,
    isImageAttachment,
    isVideoAttachment,
    isAudioAttachment
} from '@photon-ai/imessage-kit'

const msg = await sdk.getMessages({ hasAttachments: true, limit: 1 })
const attachment = msg.messages[0].attachments[0]

if (await attachmentExists(attachment)) {
    const size = await getAttachmentSize(attachment)
    
    if (isImageAttachment(attachment)) {
        await downloadAttachment(attachment, '/path/to/save.jpg')
    }
}
```

### Supported File Types

- **Documents**: PDF, DOC, DOCX, XLS, XLSX, PPT, PPTX, TXT, RTF
- **Images**: JPG, PNG, GIF, HEIC, WEBP, AVIF
- **Contact Cards**: VCF (vCard)
- **Data Files**: CSV, JSON, XML
- **Archives**: ZIP, RAR, 7Z
- **Media**: MP4, MOV, MP3, M4A

---

## Scheduling

> Examples: [14-scheduled-messages.ts](./examples/14-scheduled-messages.ts) | [15-smart-reminders.ts](./examples/15-smart-reminders.ts)

### Scheduled Messages

```typescript
import { IMessageSDK, MessageScheduler } from '@photon-ai/imessage-kit'

const sdk = new IMessageSDK()
const scheduler = new MessageScheduler(sdk, { debug: true }, {
    onSent: (msg, result) => console.log(`✅ Sent: ${msg.id}`),
    onError: (msg, error) => console.error(`❌ Failed: ${error.message}`),
    onComplete: (msg) => console.log(`🏁 Completed: ${msg.id}`)
})

// One-time message
const id = scheduler.schedule({
    to: '+1234567890',
    content: 'Reminder!',
    sendAt: new Date(Date.now() + 5 * 60 * 1000)  // 5 minutes
})

// Recurring daily
scheduler.scheduleRecurring({
    to: '+1234567890',
    content: 'Good morning! ☀️',
    startAt: new Date('2025-01-01T08:00:00'),
    interval: 'daily',  // 'hourly' | 'daily' | 'weekly' | 'monthly' | number
    endAt: new Date('2025-12-31')
})

// Manage
scheduler.reschedule(id, newDate)
scheduler.cancel(id)
scheduler.getPending()

// Persistence
const data = scheduler.export()
scheduler.import(data)

// Cleanup
scheduler.destroy()
```

### Smart Reminders

A human-friendly wrapper for scheduling with natural language:

```typescript
import { IMessageSDK, Reminders } from '@photon-ai/imessage-kit'

const sdk = new IMessageSDK()
const reminders = new Reminders(sdk)

// Relative time
reminders.in('5 minutes', '+1234567890', 'Take a break!')
reminders.in('2 hours', '+1234567890', 'Call the client')
reminders.in('1 day', '+1234567890', 'Follow up')

// Specific time
reminders.at('5pm', '+1234567890', 'End of day review')
reminders.at('tomorrow 9am', '+1234567890', 'Morning standup')
reminders.at('friday 2pm', '+1234567890', 'Weekly sync')

// Exact date
reminders.exact(new Date('2025-12-25T10:00:00'), '+1234567890', 'Merry Christmas!')

// Manage
reminders.list()    // List pending
reminders.count()   // Count pending
reminders.cancel(id)
reminders.destroy()
```

**Supported formats:**
- Duration: `"5 minutes"`, `"2 hours"`, `"1 day"`, `"30 seconds"`, `"1 week"`
- Time: `"5pm"`, `"5:30pm"`, `"17:30"`
- Day + Time: `"tomorrow 9am"`, `"friday 2pm"`

---

## Plugin System

> Example: [11-plugin.ts](./examples/11-plugin.ts)

```typescript
import { loggerPlugin } from '@photon-ai/imessage-kit'

// Built-in logger
sdk.use(loggerPlugin({
    level: 'info',
    colored: true
}))

// Custom plugin
sdk.use({
    name: 'my-plugin',
    onInit: async () => console.log('Initialized'),
    onBeforeSend: async (to, content) => {
        console.log('Sending to:', to)
        return { to, content }
    },
    onAfterSend: async (result) => {
        console.log('Sent:', result)
    },
    onDestroy: async () => console.log('Destroyed')
})
```

---

## Error Handling

> Example: [12-error-handling.ts](./examples/12-error-handling.ts)

```typescript
import { SendError, DatabaseError, PlatformError } from '@photon-ai/imessage-kit'

try {
    await sdk.send('+1234567890', 'Hello')
} catch (error) {
    if (error instanceof SendError) {
        console.error('Send failed:', error.message)
    } else if (error instanceof DatabaseError) {
        console.error('Database error:', error.message)
    } else if (error instanceof PlatformError) {
        console.error('Platform error:', error.message)
    }
}
```

---

## Examples

Run any example with Bun:

```bash
bun run examples/<filename>.ts
```

### Getting Started
- [01-send-text.ts](./examples/01-send-text.ts) - Basic text message
- [02-send-image.ts](./examples/02-send-image.ts) - Send images
- [03-send-file.ts](./examples/03-send-file.ts) - Send files

### Message Operations
- [05-query-messages.ts](./examples/05-query-messages.ts) - Query messages
- [09-batch-send.ts](./examples/09-batch-send.ts) - Batch sending
- [10-get-sent-message.ts](./examples/10-get-sent-message.ts) - Get sent message

### Chats & Groups
- [04-send-group.ts](./examples/04-send-group.ts) - Send to group
- [06-list-chats.ts](./examples/06-list-chats.ts) - List chats

### Real-time & Automation
- [07-watch-messages.ts](./examples/07-watch-messages.ts) - Watch messages
- [08-auto-reply.ts](./examples/08-auto-reply.ts) - Auto-reply bot
- [13-watch-own-messages.ts](./examples/13-watch-own-messages.ts) - Watch own messages

### Scheduling
- [14-scheduled-messages.ts](./examples/14-scheduled-messages.ts) - Scheduled messages
- [15-smart-reminders.ts](./examples/15-smart-reminders.ts) - Smart reminders

### Advanced
- [11-plugin.ts](./examples/11-plugin.ts) - Custom plugin
- [12-error-handling.ts](./examples/12-error-handling.ts) - Error handling

---

## API Reference

### Core Methods

| Method | Description |
|--------|-------------|
| `getMessages(filter?)` | Query messages with filters |
| `getUnreadMessages()` | Get unread messages grouped by sender |
| `listChats(options?)` | List chats with filtering/sorting |
| `send(to, content)` | Send text, images, and/or files |
| `sendFile(to, path, text?)` | Send a single file |
| `sendFiles(to, paths, text?)` | Send multiple files |
| `sendBatch(messages)` | Send multiple messages concurrently |
| `message(msg)` | Create message processing chain |
| `startWatching(events?)` | Start monitoring new messages |
| `stopWatching()` | Stop monitoring |
| `use(plugin)` | Register plugin |
| `close()` | Close SDK and release resources |

### Types

```typescript
interface Message {
    id: string
    guid: string
    text: string | null
    sender: string
    senderName: string | null
    chatId: string
    isGroupChat: boolean
    isFromMe: boolean
    isRead: boolean
    service: 'iMessage' | 'SMS' | 'RCS'
    attachments: Attachment[]
    date: Date
    // Reaction fields
    isReaction: boolean
    reactionType: 'love' | 'like' | 'dislike' | 'laugh' | 'emphasize' | 'question' | null
    isReactionRemoval: boolean
    associatedMessageGuid: string | null
}

interface SendResult {
    sentAt: Date
    message?: Message  // Available if watcher is running
}
```

---

## Requirements

- **OS**: macOS only
- **Runtime**: Node.js >= 18.0.0 or Bun >= 1.0.0
- **Permissions**: Full Disk Access

---

## LLMs

Download `llms.txt` for language model context:

- [Download llms.txt](./llms.txt)

### Context7 MCP

- [Context7 Docs](https://context7.com/photon-hq/imessage-kit)

Add [Context7 MCP](https://context7.com/docs/installation) to your IDE, then use:

```
use context7: photon-hq/imessage-kit
```

---

## License

[MIT License](./LICENSE)

---

**Note**: This SDK is for educational and development purposes. Always respect user privacy and follow Apple's terms of service.
