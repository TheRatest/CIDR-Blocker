<p align="center">
	<img alt="CIDR Blocker" src="https://github.com/CIDR-Blocker/CIDR-Blocker/blob/master/assets/img/CIDR_Blocker.png?raw=true" height="250" width="250">
</p>

<p align="center">
	Blocks CIDR (Classless Inter-Domain Routing) IP Ranges
</p>

---

# Console Commands

- **sm_cidr_ban \<ip> \<ban reason\> \<comment\>** Ban a CIDR (Example: `sm_cidr_ban "89.108.121.0/24" "Blocked IP" "Reg.ru"`)
- **sm_cidr_ban \<ip> \<ban reason\> \<comment\>** Unban a CIDR (Example: `sm_cidr_unban "89.108.121.0/24"`)
- **sm_cidr_whitelist \<ip/steamid2\> \<comment\>** Ban a CIDR (Example: `sm_cidr_whitelist "89.108.121.120" "Exception for me because i said so"` or `sm_cidr_whitelist "STEAM_0:1:522065531"`)

# ConVar

- **sm_cidr_log** Enable blocked logging [Default: **0.0**] (Min: **0.0**) (Max: **1.0**)

# Database Structure

### CIDR_LIST

- **id** - Auto incremental ID (**Filled in automatically**)

- **cidr** - CIDR to block

- **kick_message** - Message to display when kicked

- **comment** - Helps you keep track

### CIDR_WHITELIST

- **id** - Auto incremental ID (**Filled in automatically**)

- **type** - Whitelist type (**steam** OR **ip**)

- **identity** - Depending on the whitelist type (**steamid32** OR **IP**)

- **comment** - Helps you keep track

### CIDR_LOG (Used when `sm_cidr_log` is **1.0**)

- **id** - Auto incremental ID (**Filled in automatically**)

- **ip** - Client's connecting IP

- **steamid** - Client's SteamID32

- **name** - Client's connecting name

- **cidr** - CIDR that was triggered

- **time** - Time it was blocked

# Installation

1. Extract **CIDR_Blocker.smx** to **/addons/sourcemod/plugins**
2. Create **cidr_blocker** entry in your database.cfg
3. (Optional | Recommended) Import https://github.com/CIDR-Blocker/CIDR-Blocker/blob/master/imports/datacenters.sql into `cidr_list` table


# Download

Download the latest version from the [release](https://github.com/CIDR-Blocker/CIDR-Blocker/releases) page

# Resources

- ASN Blocklist - https://www.enjen.net/asn-blocklist/

- Pre-made SQL script of most datacenters - https://github.com/CIDR-Blocker/CIDR-Blocker/blob/master/imports/datacenters.sql

# License

GPL-3.0

Icon made by <a href="http://www.freepik.com/" target="_blank">Freepik</a> from <a href="http://www.flaticon.com/" target="_blank">http://www.flaticon.com/</a>
