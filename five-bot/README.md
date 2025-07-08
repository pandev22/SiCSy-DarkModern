# Five-Bot 🤖

Five-Bot est un **bot Discord** complet pour la gestion de serveurs communautaires, avec des fonctionnalités avancées de **modération**, **tickets**, **suggestions**, **whitelists multi-serveurs**, **captcha anti-raid**, **logs détaillés**, et bien plus !

---

## ✨ Fonctionnalités principales

- 🛡️ **Modération avancée** : mute, ban, kick, warn, casier d'infractions, gestion automatique des sanctions.
- 🎫 **Tickets d'assistance** : création, gestion, ajout d'utilisateurs, logs et transcripts.
- 💡 **Suggestions** : formulaire de suggestion avec validation par réactions.
- 🟢 **Whitelist multi-serveurs** : gestion centralisée de la whitelist sur plusieurs serveurs Discord.
- 🧩 **Captcha anti-raid** : vérification par image captcha à l'arrivée, avec gestion de l'âge minimum du compte.
- 📝 **Logs détaillés** : journalisation de toutes les commandes et interactions dans des fichiers journaux.
- 🧹 **Commandes utilitaires** : suppression de messages, création d'embeds personnalisés, ping, etc.

---

## 🛠️ Commandes Slash

### `/moderation`
- 🔇 **mute** : Mute un utilisateur pour une durée donnée.
- 🔨 **ban** : Ban un utilisateur, temporairement ou définitivement.
- 👢 **kick** : Expulse un utilisateur.
- ⚠️ **warn** : Avertit un utilisateur, avec sanctions automatiques après plusieurs avertissements.
- 📋 **casier** : Affiche le casier d'infractions d'un utilisateur, possibilité de supprimer une infraction.

### `/ticket`
- 🎟️ Crée un ticket d'assistance, choix de la catégorie, gestion par boutons (fermer, ajouter un utilisateur), transcript automatique à la fermeture.

### `/suggestion`
- 💬 Ouvre un formulaire pour proposer une suggestion, qui sera postée dans un salon dédié avec réactions pour voter.

### `/whitelist`
- ✅ Ajoute un utilisateur à la whitelist sur plusieurs serveurs, avec gestion des rôles par service.

### `/embed`
- 🖼️ Crée un embed personnalisé (titre, description, couleur, image) via un formulaire (**admin uniquement**).

### `/clear`
- 🧹 Supprime un nombre précis de messages dans un salon (**admin uniquement**).

### `/ping`
- 🏓 Répond `Pong!` pour tester la réactivité du bot.

---

## 🔒 Sécurité & Automatisation

- 🧩 **Captcha anti-raid** : canal temporaire, image captcha, 3 essais, kick automatique en cas d'échec ou de timeout.
- ⏳ **Âge minimum du compte** : configurable, kick automatique si le compte est trop récent.
- 📝 **Logs** : toutes les commandes et interactions sont enregistrées dans `logs/all/` par date.
- 🛡️ **Gestion des permissions** : la plupart des commandes sensibles sont réservées aux rôles admins ou configurables.

---

## ⚙️ Configuration

Le bot utilise un fichier `.env` pour la configuration. Voici les variables principales à définir :

```env
DISCORD_TOKEN=VotreTokenIci
CLIENT_ID=VotreClientID
GUILD_ID=IDDuServeurPrincipal
MAIN_GUILD_ID=IDDuServeurPrincipal
SYNC_GUILD_IDS=ID1,ID2,ID3
ADMIN_ROLES=IDRoleAdmin1,IDRoleAdmin2
WHITELIST_ROLE=NomDuRoleWhitelist
WHITELIST_FILE=whitelist.json
WHITELIST_SERVICES=Service1,Service2,Service3
WHITELIST_ALLOWED_ROLES=Role1,Role2
TICKET_CATEGORIES=Support,Payement,Autre
TICKET_CATEGORY_ID=IDCategorieTicket
TICKET_ROLES=IDRoleSupport1,IDRoleSupport2
TICKET_LOG_CHANNEL_ID=IDSalonLogsTickets
SUGGESTION_CHANNEL_ID=IDSalonSuggestions
ENABLE_CAPTCHA=true
CAPTCHA_ROLE=NomOuIDRoleCaptcha
CAPTCHA_CATEGORY_ID=IDCategorieCaptcha
MIN_ACCOUNT_AGE=3d
WELCOME_CHANNEL_ID=IDSalonBienvenue
WARN_KICK=3
WARN_BAN=5
```

> **Remarque** : *Adaptez les IDs et noms de rôles/catégories à votre serveur.*

---

## 🚀 Installation

1. **Clonez le repo et placez-vous dans le dossier :**
   ```bash
   git clone <repo>
   cd five-bot
   ```
2. **Installez les dépendances :**
   ```bash
   npm install
   ```
3. **Créez un fichier `.env` à la racine et remplissez-le selon la section précédente.**
4. **Déployez les commandes slash :**
   ```bash
   node deploy-commands.js
   ```
5. **Lancez le bot :**
   ```bash
   node index.js
   ```

---

## 🗂️ Structure du projet

```
commands/      # Toutes les commandes slash (modération, ticket, suggestion, etc.)
midelware/     # Middlewares pour captcha, tickets, logs
logs/          # Logs d'activité et de modération
whitelist.json # Fichier de whitelist multi-serveurs
```

---

## 📦 Dépendances principales

- [`discord.js`](https://discord.js.org/) v14
- [`canvas`](https://www.npmjs.com/package/canvas) *(pour le captcha)*
- [`dotenv`](https://www.npmjs.com/package/dotenv)
- [`ms`](https://www.npmjs.com/package/ms)
- [`node-fetch`](https://www.npmjs.com/package/node-fetch)
- [`cfx-api`](https://www.npmjs.com/package/cfx-api) *(optionnel, pour intégration FiveM)*

---

## 💬 Support & Contributions

N'hésitez pas à **ouvrir une issue** ou une **pull request** pour toute amélioration ou question !
