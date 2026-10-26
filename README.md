# BesiegedAlert

Standalone Besieged notifications in a wide, draggable gold-bordered banner. Smaller Georgia text, a translucent dark background, and horizontal army information keep the display compact.

Preparing stays hidden. Advancing and attacking armies appear automatically.

## Installation

Place `BesiegedAlert.lua` and `status.lua` together in:

```text
Windower/addons/BesiegedAlert
```

Load the addon:

```text
//lua load BesiegedAlert
```

No VanaPortal client, TVR completion, or other Besieged addon is required. Avoid running multiple Besieged polling addons on one client.

## Startup

Loading is manual unless you add the following to your own Windower startup configuration:

```text
lua load BesiegedAlert
```

No character-specific startup rules or hotkeys are bundled. Settings are created automatically with the banner enabled.

## Commands

### Preview the banner for ten seconds

```text
//ba preview
```

Displays a local sample banner without sending external alerts.

### Enable automatic display

```text
//ba on
```

The banner appears when an army is advancing or attacking. This does not force a preview.

### Hide the banner

```text
//ba off
```

Status polling continues while the banner is hidden.

### Toggle automatic display

```text
//ba hud
```

### Show the latest known status

```text
//ba status
```

Prints the cached army status and how old the information is.

### Request fresh status

```text
//ba ping
```

Alternatively:

```text
//ba check
```

Manual requests respect a 125-second minimum between requests.

### Enable debug messages

```text
//ba debug on
```

### Disable debug messages

```text
//ba debug off
```

### Save the banner position

Drag the text to move the banner, then run:

```text
//ba save
```

## Display Behavior

- The banner shows armies that are advancing or attacking.
- Preparing and inactive states remain hidden.
- Multiple active armies appear together.
- Automatic checks run every five minutes.
- The banner hides when a new report shows no advancing or attacking armies.
- Stale reports are hidden if fresh updates stop arriving.

Because status is checked periodically, the display may take up to five minutes to reflect a change.

## Optional External Alerts

A background integration feature can be enabled with separate setup to forward Besieged alerts from FFXI to Discord, mobile-phone notifications, or other destinations supported by a compatible notification service.

External delivery is not included or enabled by default and requires that service and its configuration.

**Proprietary code notice:** The custom external-alert integration code is reserved for private use. All applicable copyrights are reserved by its respective rights holders. This release grants no permission to copy, redistribute, modify, or use that private integration code without prior written authorization. This restriction applies specifically to the private external-alert integration, not to the standalone banner functionality.

## Validation

Offline state decoding, UI lifecycle, and command controls were checked. The banner appearance and transparency have been confirmed in-game. Automatic detection during an actual Besieged is still awaiting live confirmation.

## Acknowledgments

Status layout was verified against the Meliora/Xurion Besieged addon. BesiegedAlert is an independent implementation with no dependency on that addon.

---

Author: Soliserio
