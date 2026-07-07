<img width="1376" height="768" alt="litevillagertrade_banner" src="https://github.com/user-attachments/assets/8f9f6f9d-3057-43b0-ae28-69bb17008d09" />

<p align="center">
  <a href="https://bstats.org/plugin/bukkit/LiteVillagerTrade/YOUR_BSTATS_ID">
    <img src="https://bstats.org/signatures/bukkit/LiteVillagerTrade.svg" width="1200" alt="LiteVillagerTrade bStats statistics">
  </a>
</p>

**LiteVillagerTrade** is a next-generation, high-performance, and **Folia-ready** shopkeepers-style trading plugin for Minecraft servers. Built from the ground up for modern server environments, it allows server administrators to set up customized merchant shops with infinite stock (Admin Shops).

---

## 🌟 Key Features

### 📦 Admin Shops with Infinite Stock
* **Admin Shops**: Sell items with infinite stock—perfect for server marketplaces, admin-run trade booths, and server-wide economy shops.

---

### 💳 Economy & Custom Currency Support

![Vault Integration](assets/vault_currency_banner.jpg)

LiteVillagerTrade offers robust integration with Vault and PlaceholderAPI:
* **Vault Integration**: Charge players virtual money for trades. Fares are automatically debited from their Vault balance.
* **Custom PAPI Currencies**: Define any custom currency using PlaceholderAPI (e.g., PlayerPoints, TokenManager, Coins, or custom variables) with custom GUI items, formatting, and balances.
* **NBT-Safe Lore Cleanup**: Price lore is temporarily appended to items inside the merchant UI, but is **100% stripped and cleaned** upon successful purchase, ensuring items are returned to players with their original names, durability, and custom NBT tags intact.

---

### 🎭 Visual customizer and NPC models

![NPC Customization](assets/fancynpcs_customization_banner.jpg)

Customize your shopkeeper's appearance directly inside an interactive GUI:
* **NPC Types**: Cycle shopkeepers between standard Minecraft `VILLAGER`, `WANDERING_TRADER`, or **FancyNPC Player Models**.
* **Skin customizer**: Click to enter any player skin name (e.g. `eoxyn`, `Herobrine`) in chat to apply it dynamically to your FancyNPC player model.
* **Outfit Colors**: Cycle clothing biome styles (`desert`, `snow`, `taiga`, `savanna`, `swamp`, `jungle`, `plains`).
* **Tool/Item Icons**: Customization menus display beautiful, theme-matching item icons representing each villager profession and outfit color block in real-time.
* **AI & Gaze Control**: Toggle movement/AI or NPC turning (FancyNPC turn-to-player behavior) with a single click.

---

## 🛠 Commands & Permissions

### Commands Table

| Command | Description | Permission |
| :--- | :--- | :--- |
| `/lvt create [title]` | Spawns a standard Admin Shop Villager. | `litevillagertrade.create` |
| `/lvt create npc <skin> [title]` | Spawns a Player-model FancyNPC Admin Shop. | `litevillagertrade.create` |
| `/lvt create villager [title]` | Spawns a Bukkit Villager Admin Shop. | `litevillagertrade.create` |
| `/lvt remove <name>` | Deletes the shop matching that name. | `litevillagertrade.remove` |
| `/lvt edit <name>` | Opens the customization menu for that shop. | `litevillagertrade.edit` |
| `/lvt move <name>` | Teleports the specified shop NPC to your location. | `litevillagertrade.move` |
| `/lvt reload` | Reloads the configuration and messages. | `litevillagertrade.reload` |

* **Normal User Shift-click Protection**: Only shop owners or admins can open the editor GUI by **Shift-Right-Clicking** the shopkeeper. Normal players right-clicking will only open the standard trade/merchant GUI.
* **Name-Based Subcommands**: Removal, editing, and movement commands are strictly name-based and support smart tab auto-completion for convenience.

---

## ⚙ Configuration Examples

### `config.yml`
```yaml
# Database configuration (supports sqlite and mysql)
storage:
  type: "sqlite" # sqlite, mysql
  sqlite:
    file: "database.db"
  mysql:
    host: "localhost"
    port: 3306
    database: "minecraft"
    username: "root"
    password: ""

# Custom PAPI Currencies
currencies:
  playerpoints:
    display-name-gui: "&d%price% Points"
    placeholder: "%playerpoints_points%"
    take-command: "points take %player% %price%"
    item-material: "AMETHYST_SHARD"
    item-name: "&d&lPlayerPoints"
```

### `messages.yml`
```yaml
# Premium hex and mini-message support
trade:
  cost-display: "<#888888>Price: <#ffd54f>$%price% Vault</#ffd54f></#888888>"
  insufficient-funds: "<#ef5350>Insufficient funds! Required: $%price%</#ef5350>"
```

---

## 💻 Developer API Events

Developers can hook into LiteVillagerTrade lifecycle events:
* `ShopCreateEvent`: Triggered when a new shop NPC is created.
* `ShopDeleteEvent`: Triggered when a shop NPC is removed.
* `PlayerOpenShopEvent`: Triggered when a player interacts with a shopkeeper.
* `PlayerPurchaseEvent`: Triggered when a transaction is completed in a shop.
eper.
* `PlayerPurchaseEvent`: Triggered when a transaction is completed in a shop.
