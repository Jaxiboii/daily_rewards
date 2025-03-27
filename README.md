# Daily Rewards System for FiveM

Enhance your FiveM server with a real-life time daily rewards system! Players can open a reward crate every day, receiving customizable rewards like money, items, or weapons, all integrated with ESX, OX Inventory, and OX Lib.

## Features
- ⏰ **Real-Time 24-Hour Cooldown**: Players can claim a reward once every 24 hours, tracked in real-time using a MySQL database, independent of server restarts or player online status.
- 📅 **Monthly Reward Grid**: Displays a crate for each day of the current month, with visual indicators for claimed, available, and locked rewards.
- 🎁 **Configurable Rewards**: Define rewards (money, items, weapons) with custom rarities (common, rare, epic, legendary) and probabilities in `config.lua`.
- 🖼️ **Interactive UI**: Built with HTML, CSS, and JavaScript, featuring a timer, reward pop-ups, and a chances overlay showing possible rewards.
- 💾 **Database Sync**: Player progress (last claim, current day, claimed days) is stored in a MySQL database for persistence.
- 🤝 **ESX Integration**: Seamlessly integrates with the ESX framework for player management and inventory handling.
- 🔊 **Sound Effects**: Includes an optional sound effect when claiming a reward.

Give your players a reason to log in daily with this engaging and rewarding system! 🚀

---

## 🔥 Upcoming Features
- 🪙 **Coin Shop System** – Earn coins with each crate opening, redeemable for exclusive items, vehicles, or perks.
- 🎨 **Improved UI** – A more polished and interactive interface with additional functionalities.
- ⚙️ **Further Optimization** – Continued performance enhancements for larger servers.

Stay tuned for these exciting updates! 🔥

---

## 💻 Requirements
- [ESX Framework](https://github.com/esx-framework/es_extended)
- [OX_Lib](https://github.com/overextended/ox_lib)
- [OX_Inventory](https://github.com/overextended/ox_inventory)
- [Oxmysql](https://github.com/overextended/oxmysql)

---

## 📥 Installation
1. Download the latest release from this repository.
2. Extract the folder into your server's `resources` directory.
3. Rename the folder to `daily_rewards` (if not already named).
4. Add `ensure daily_rewards` to your `server.cfg`.
5. Configure the `config.lua` file with your desired rewards and settings.
6. Ensure all dependencies are installed and running.
7. Create the database table using the SQL below.
8. Restart your server or use `refresh` followed by `start daily_rewards`.

### SQL Table Creation
```sql
CREATE TABLE IF NOT EXISTS `daily_rewards` (
  `identifier` varchar(50) NOT NULL,
  `last_claim` bigint(20) DEFAULT 0,
  `current_day` int(11) DEFAULT 1,
  `claimed_days` text DEFAULT '[]',
  `current_month` varchar(2) DEFAULT NULL,
  `current_year` varchar(4) DEFAULT NULL,
  PRIMARY KEY (`identifier`)
);
