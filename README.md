# Name Codex for Microsoft 365

Consistent naming conventions for your Microsoft 365 tenant.

Name Codex is a single-page, fully client-side tool for generating standardized names (and, for some object types, descriptions) for common Microsoft 365 and Microsoft Entra ID objects. Pick an object type, pick a naming pattern, fill in a few fields, and get a live-previewed name you can copy straight into the Microsoft 365 admin center, Entra admin center, or Intune.

No build step, no backend, no external dependencies — it's a single `index.html` file you can open directly in a browser or host anywhere as a static file.

## Supported object types & patterns

| Object type | Patterns |
|---|---|
| **Conditional Access Policy** | Generic, Enterprise, MSP, Project, Extended, Microsoft Recommended, Emergency Access |
| **App Registration** | Generic, Enterprise, MSP, Project |
| **Groups** | Security Group, M365 Group, Distribution List, Shared Mailbox, Room/Equipment, PIM Group |
| **Endpoint Security** | Windows, macOS, Linux |
| **Intune** | Compliance Policy, Configuration Policy, App Protection, App Configuration |
| **Defender for Office 365** | Anti-Phishing, Anti-Spam, Anti-Malware, Safe Attachments, Safe Links, Quarantine |

Each pattern defines a fixed, ordered set of fields (for example, Security Group: Prefix, Membership Type, Department, Function, Scope, Environment). Every field is optional — leave one blank and its segment is simply omitted from the generated name.

## Key features

- **Live name preview** — segments update as you type, shown both as a joined string and as individual color-coded chips.
- **Configurable separator** — hyphen (`-`) or underscore (`_`).
- **Configurable case style** — PascalCase, UPPERCASE, lowercase, or As Typed (verbatim, including spaces and punctuation).
- **Custom prefixes** — most patterns offer a curated prefix dropdown (e.g. `SEC` / `SG` / `GRP` for security groups) plus a Custom option that accepts any text, dashes and all.
- **Dynamic membership support** — Security Group and M365 Group patterns can be marked Role Assignable, Dynamic User, or Dynamic Device, which swaps in the matching Attribute / Attribute Value fields for building Entra ID dynamic membership rules.
- **Description generator** — for App Registration and Groups, a plain-language description is generated alongside the name, ready to paste into the object's Description field.
- **Copy AI Prompt** — packages the current field values into a ready-to-use prompt for asking an AI assistant to draft alternative descriptions.
- **Recent Names history** — the last 10 generated names are kept locally (with a Clear button to wipe them) so you can quickly reuse or compare earlier results.
- **Light/dark theme**, remembered between visits.

## Usage

1. Open `index.html` in any modern browser (double-click it, or host it on any static web server).
2. Choose an object type from the cards at the top.
3. Choose a naming pattern.
4. Fill in the fields you care about — everything is optional.
5. Adjust Separator and Case Style to match your organization's convention.
6. Copy the generated name, and (where available) the generated description or AI prompt.

## Data & privacy

Name Codex makes no network calls and sends no data anywhere. The only thing it persists is in your browser's `localStorage`:

- `ngen-theme` — your last-used light/dark theme.
- `ngen-history` — your last 10 generated names, for quick reference.

Everything else lives only in memory for the current page session.

## Project structure

- `index.html` — the application (markup, styles, and logic all in one file).
- `namecodex.png`, `*.svg` — logo and icon assets used by the UI.
- `index - Backup *.html`, `index_*-beta.html` — earlier working versions, kept for reference.

## Credits

Built by [Matej Klemenčič](https://www.matej.guru).
