# Wavo Privacy Policy

**Effective date:** 1 November 2026

This Privacy Policy explains what information **Wavo** (“the bot”, “we”, “us”) processes when you use the Discord music bot and related webhooks. It should be read with the [Terms of Service](./TERMS.md).

Wavo is operated by the WavoBot team. We are not Discord, Top.gg, YouTube, or Google.

## 1. Who this applies to

We process data when:

- Someone invites Wavo to a Discord server
- Users run commands, press player buttons, or use ChatPlay
- A server stays in 24/7 mode or uses radio
- Someone votes for Wavo on Top.gg
- You join our support Discord

If you do not want this processing, remove Wavo from your server and stop using the Service.

## 2. What we collect

We do **not** ask you to create a Wavo password or profile. Identifiers come from Discord.

### Discord identifiers and server settings

We store per-server configuration such as:

- Discord **guild (server) ID**
- ChatPlay channel ID and player message ID, and ChatPlay options (enabled, slowmode, auto-delete requests, pin player, smart filter)
- 24/7 flag, **bound voice channel ID**, and last time someone listened in that channel
- Default volume, autoplay preference, and language/locale override
- Optional DJ-related fields reserved for future use

We store per-user records tied to a Discord **user ID** for vote-prompt snoozes and vote-perk expiry.

We do not store Discord email addresses, passwords, or payment cards. We cannot read your Discord password.

### Commands and player usage

When you play a track we may store:

- Guild ID and **user ID of the requester**
- Track **title**, **artist**, **source URL**, duration, and time played

This powers `/toptracks` and internal operations dashboards. We do not store the audio file.

Analytics events (for example guild join/leave, plays, limit hits, votes) include a timestamp, event type, guild ID, and a small metadata payload. Raw analytics events are retained for about **90 days**. Aggregated daily counts may be kept longer.

### Message Content (ChatPlay)

Wavo requests Discord’s **Message Content** intent so ChatPlay can treat a message in the configured channel as a song request.

We **process** that message text to search and queue a track. We **do not** keep a full log of ChatPlay message bodies. If auto-delete is on, Wavo deletes the request message in Discord after handling it. Track metadata and requester ID may still be stored as described above.

Messages outside the ChatPlay channel are not used for playback. Direct messages to the bot are ignored except when we send a vote thank-you you cannot receive in a guild channel.

### Voice

Wavo joins voice channels you select in order to play audio. We do **not** record, transcribe, or store voice or video from those channels.

### Votes (Top.gg)

If you vote, Top.gg may send us your Discord user ID, a timestamp, and optional query parameters (such as a guild ID). We use that to grant perks, thank you in DM or in the music channel, and optionally assign a voter role on our support server.

### Incidents and operations

We store operational incident notes (component name and description, with node names anonymized) for `/status`. Hosting logs (Railway or similar) may contain technical errors for a short time.

### Backups

The SQLite database (guild settings, users, analytics, track plays) may be backed up so we can recover after a failure.

## 3. How we use information

We use this information to:

- Run playback, queues, ChatPlay, radio, and 24/7
- Remember language and volume defaults
- Enforce resource and vote-perk limits
- Show `/toptracks`, `/status`, and internal ops metrics
- Debug outages and abuse
- Credit votes and contact you about the bot in Discord

We do **not** sell your personal data. We do not use ChatPlay messages to train third-party AI models.

## 4. Legal bases (EEA/UK)

Where GDPR or UK GDPR applies, we rely on:

- **Legitimate interests** — operating a music bot people invited, preventing abuse, measuring reliability
- **Contract** — providing the Service you requested by inviting or using the bot
- **Consent** — where Discord requires it (for example Message Content in your server) or optional voting

You can object by removing the bot or asking us to delete guild/user records (see section 8).

## 5. Sharing

We share data only as needed to run the Service:

| Recipient | Why |
|-----------|-----|
| **Discord** | Gateway, commands, messages, voice |
| **Lavalink / audio host** | Resolve and stream the tracks or radio URLs you request (queries and stream URLs leave our bot process) |
| **Top.gg** | Server-count stats and inbound vote webhooks |
| **Hosting provider** | Run the bot and store the database |
| **You / server admins** | Leaderboards and player UI visible in the server |

Streaming platforms (for example YouTube) receive whatever the Lavalink node requests when you play a link or search. Their privacy policies apply to that hop.

We may disclose information if required by law or to protect the Service, our users, or others.

## 6. Retention

| Data | Typical retention |
|------|-------------------|
| Guild settings | Until the bot is removed and we purge the row, or you ask us to delete it |
| 24/7 / ChatPlay IDs | Until disabled or deleted |
| Vote perk / snooze | Until the timestamps expire, then the row may remain empty or be removed |
| Track plays | Until deleted on request or as part of a storage cleanup |
| Analytics events | About 90 days |
| Backups | Rotated; older copies are overwritten |
| Discord message content | Not stored by us as a message log |

Removing Wavo from a server stops new collection for that guild. Historical rows may remain until we delete them; contact us if you want them removed sooner.

## 7. International transfers

The bot, database, Lavalink nodes, and Discord may process data in the United States, Europe, or other countries. If you use Wavo from the EEA/UK, that is an international transfer necessary to provide the bot.

## 8. Your rights

Depending on your country, you may have rights to access, correct, delete, or export personal data, or to object to certain processing.

To exercise them, open a ticket in the [support server](https://discord.gg/MRjEUhDCpZ) from the Discord account the request concerns, and include the **user ID** and any **server ID**. We may need to verify you administer that server before deleting guild-wide data (this would remove ChatPlay/24/7 settings and that guild’s play history).

You can also:

- Change or clear the server language with `/language`
- Disable or delete ChatPlay with `/chatplay`
- Turn off 24/7 with `/247`
- Kick the bot from the server

Discord’s own privacy tools are described in [Discord’s Privacy Policy](https://discord.com/privacy).

## 9. Children

The Service is not directed at children under 13 (or the minimum age in your country). We do not knowingly store data from children below that age. If you believe we have, contact us and we will delete it.

## 10. Security

We restrict access to the production database and bot token, use HTTPS for webhooks where configured, and do not put secrets in these public documents. No method of transmission or storage is completely secure.

## 11. Automated decisions

Vote perks and queue/autoplay limits are applied automatically from vote webhooks and usage counts. They do not produce legal effects about you beyond in-bot limits.

## 12. Changes

We will post updates in this repository and change the effective date. Material changes may also be announced in the support server.

## 13. Contact

Privacy requests: [Wavo support server](https://discord.gg/MRjEUhDCpZ) or the WavoBot GitHub organization.

## Contributors

Wavo is built and operated with contributions from **Mitch** and **Ramkrishna**.
