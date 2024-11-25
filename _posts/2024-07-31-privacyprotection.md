---
title: 隐私保护工具推荐

date: 2024-07-31 12:00:00 +0800

categories: [Privacy]

tags: [privacy]

pin: false

math: false

image: https://fanwb.oss-cn-beijing.aliyuncs.com/img/camera.jpg

---

> "We must defend our own privacy if we expect to have any."  *— A Cypherpunk's Manifesto*




本文是个人使用体验较好的各类隐私保护工具的推荐，以开源软件为主，不定期更新。

## 网页浏览

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/logo.fedb52c912d6.svg" alt="mozilla.org/media/protocol/img/logos/firefox/logo.fedb52c912d6.svg" style="zoom: 30%;" /> Firefox

完全开源的浏览器，支持大量隐私插件，内置反追踪功能，可以阻止第三方 Cookie，可以设置 DNS over HTTPS 加密 DNS 查询。安装后需要进行一定的安全配置，参考 [@arkenfox user.js](https://github.com/arkenfox/user.js/) 、[restore privacy](https://restoreprivacy.com/firefox-privacy/) 或 [12bytes](https://codeberg.org/12bytes/firefox-config-guide)。

- **官网：**[mozilla.org/firefox](https://www.mozilla.org/firefox)
- **隐私：**[tosdr.org/en/service/188](https://tosdr.org/en/service/188)
- **开源：**✅ 

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/icon.svg" alt="LibreWolf Icon" style="zoom:10%;" /> LibreWolf

LibreWolf 是 Firefox 的一个独立分支，提供更严格的默认设置，以保障用户隐私、安全性和自由。禁用 Mozilla Telemetry，切断了与 Google（Safe Browsing）的关联，内置了内容拦截器 [uBlock Origin](https://github.com/gorhill/uBlock)，隐私默认设置参考了 [Arkenfox project](https://github.com/arkenfox/user.js/) 等研究成果。

- **官网：**[librewolf.net](https://librewolf.net/)
- **隐私：**[tosdr.org/en/service/6389](https://tosdr.org/en/service/6389)
- **开源：**✅ 

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/128px-Tor_Browser_icon.svg.png" style="zoom:20%;" /> Tor Browser

Tor Browser 基于 Firefox ESR 开发，由 Tor 项目维护。基于洋葱路由技术提供匿名层，所有流量通过 Tor 网络加密传输，隐藏用户真实 IP 地址，通过多层加密和多跳转发实现匿名。速度会比普通浏览器慢，某些网站可能无法访问。

- **官网：**[torproject.org](https://www.torproject.org/)
- **隐私：**[tosdr.org/en/service/2845](https://tosdr.org/en/service/2845)
- **安卓：**[https://play.google.com/store/apps/details?id=org.torproject.torbrowser](https://play.google.com/store/apps/details?id=org.torproject.torbrowser)
- **开源：**✅



## 邮件客户端

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/ios-icon-180.png" style="zoom:15%;" /> Thunderbird

由 Mozilla 开发和维护的免费开源邮件客户端，从 v78.2.1 起内置了 OpenPGP 的加密和验签功能，可使用 [TorBirdy](https://trac.torproject.org/projects/tor/wiki/torbirdy) 扩展通过 Tor 网络路由所有流量。[Betterbird](https://github.com/Betterbird/thunderbird-patches) 等分支添加了额外功能。

- **官网：**[thunderbird.net](https://www.thunderbird.net/)
- **隐私：**[tosdr.org/en/service/3365](https://tosdr.org/en/service/3365)
- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/tuta.png" style="zoom:5%;" /> Tuta

免费的开源电子邮件服务，支持匿名注册，并提供加密日历，有免费和付费版本，支持桌面、Web和移动端。与其他加密邮件提供商不同，Tuta [不使用 OpenPGP](https://tuta.com/blog/posts/differences-email-encryption/)，而是采用了由对称和非对称加密算法（包括 AES256、RSA 2048 或 ECC (x25519) 和 Kyber-1024）构成的混合方案，在与使用 PGP 的联系人沟通时会有兼容性问题。但 Tuta 会加密更多的标头数据（如正文、附件、主题行和发件人姓名等），这是 PGP 邮件提供商无法做到的。最近 Tuta 加密算法的升级使得通过其服务存储和发送的数据能够抵御量子计算机的攻击。

- **官网：**[tuta.com](https://tuta.com/)
- **隐私：**[tosdr.org/en/service/157](https://tosdr.org/en/service/157)
- **iOS：**[apps.apple.com/us/app/encrypted-email-tuta/id922429609](https://apps.apple.com/us/app/encrypted-email-tuta/id922429609)
- **安卓：**[https://play.google.com/store/apps/details?id=de.tutao.tutanota](https://play.google.com/store/apps/details?id=de.tutao.tutanota)
- **开源：**✅



## 密码管理

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/KeePass_Logo_(2016).svg" style="zoom:10%;" /> KeePass

本地密码管理器，没有内置云同步功能（符合安全密码管理器的[黄金标准](https://keepass.info/ratings.html)）。支持高强度加密，可以生成随机密码。KeePass 客户端：[Strongbox](https://apps.apple.com/us/app/strongbox-keepass-pwsafe/id897283731)（Mac 和 iOS）、[KeePassDX](https://play.google.com/store/apps/details?id=com.kunzisoft.keepass.free)（Android）、[KeeWeb](https://keeweb.info/)（基于 Web/自托管）、[KeePassXC](https://keepassxc.org/)（Windows、Mac 和 Linux）

- **官网：**[keepass.info](https://keepass.info/)
- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/bitwarden.com.png" style="zoom:5%;" /> Bitwarden

具有云同步功能的全功能开源密码管理器，所有数据端到端加密，支持双因素认证，有免费和付费版本，支持桌面、Web和移动端。[Vaultwarden](https://github.com/dani-garcia/vaultwarden) 是 Bitwarden 服务器的自托管 Rust 实现，与 [Bitwarden 客户端](https://bitwarden.com/download/) 兼容。

- **官网：**[bitwarden.com](https://bitwarden.com/)
- **隐私：**[tosdr.org/en/service/1348](https://tosdr.org/en/service/1348)
- **iOS：**[apps.apple.com/us/app/bitwarden-password-manager/id1137397744](https://apps.apple.com/us/app/bitwarden-password-manager/id1137397744)
- **安卓：**[https://play.google.com/store/apps/details?id=com.x8bit.bitwarden](https://play.google.com/store/apps/details?id=com.x8bit.bitwarden)
- **开源：**✅



## 文件加密

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/veracrypt_210357.webp" style="zoom:10%;" /> VeraCrypt

开源的跨平台磁盘加密软件，可加密特定文件或目录，或者整个磁盘或分区。 VeraCrypt 功能丰富，支持多种加密算法和哈希算法，提供易用的 GUI，同时也有 CLI 版本和便携版本。VeraCrypt 是在 TrueCrypt 的基础上开发的。

- **官网：**[veracrypt.fr](https://www.veracrypt.fr/)
- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/11850518.png" style="zoom:7%;" /> Cryptomator

针对云文件的开源加密客户端，Cryptomator 加密时可保留单个文件结构，能透明集成各种云服务。与 VeraCrypt 相比，加密方式的可选项较少。Cryptomator 可跨平台运行，支持移动端。

- **官网：**[cryptomator.org](https://cryptomator.org/)
- **隐私：**[tosdr.org/en/service/4403](https://tosdr.org/en/service/4403)
- **iOS：** [apps.apple.com/us/app/cryptomator/id1560822163](https://apps.apple.com/us/app/cryptomator/id1560822163)
- **安卓：** [https://play.google.com/store/apps/details?id=org.cryptomator](https://play.google.com/store/apps/details?id=org.cryptomator)
- **开源：**✅



## 加密通讯

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/Signal_ultramarine_icon.png" style="zoom:11%;" /> Signal

端到端加密的跨平台即时通讯软件，所有通信内容都经过加密 ([Signal Protocol](https://en.wikipedia.org/wiki/Signal_Protocol))，不存储用户元数据，支持消息自动删除。支持已读回执、多媒体附件、音视频通话等常用功能。曾受到 Edward Snowden [推荐](https://twitter.com/Snowden/status/661313394906161152)。

- **官网：**[signal.org](https://signal.org/)
- **隐私：**[tosdr.org/en/service/528](https://tosdr.org/en/service/528)
- **iOS：**[apps.apple.com/us/app/signal-private-messenger/id874139669](https://apps.apple.com/us/app/signal-private-messenger/id874139669)
- **安卓：**[https://play.google.com/store/apps/details?id=org.thoughtcrime.securesms](https://play.google.com/store/apps/details?id=org.thoughtcrime.securesms)
- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/128px-Matrix_icon.svg.png" style="zoom:16%;" /> Matrix

去中心化的加密通讯协议，采用 Olm 和 Megolm 进行端到端加密。可以自建服务器，有 [Element](https://element.io/) 等多个客户端可选。

- **官网：**[matrix.org](https://matrix.org/)
- **隐私：**[tosdr.org/en/service/2455](https://tosdr.org/en/service/2455)
- **开源：**✅



## P2P 加密通讯

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/briar_logo_circle.png" style="zoom:13%;" /> Briar

基于 Tor 网络的点对点加密通讯工具，无中心服务器，内容存储在设备本地，支持离线消息，可直接与附近的联系人连接而无需访问互联网（使用蓝牙或 LAN）。支持安卓移动端及桌面端。

- **官网：**[briarproject.org](https://briarproject.org/)
- **隐私：**[tosdr.org/en/service/2559](https://tosdr.org/en/service/2559)
- **安卓：**[https://play.google.com/store/apps/details?id=org.briarproject.briar.android](https://play.google.com/store/apps/details?id=org.briarproject.briar.android)
- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/apple-touch-icon-57x57.png" style="zoom: 40%;" /> Jami

点对点加密聊天网络，支持音视频通话、屏幕共享、在线会议和即时消息。 支持移动端并提供跨平台 GNU 客户端。

- **官网：**[jami.net](https://jami.net/)
- **IOS：**[apps.apple.com/ca/app/jami/id1306951055](https://apps.apple.com/ca/app/jami/id1306951055)
- **安卓：**[https://play.google.com/store/apps/details?id=cx.ring](https://play.google.com/store/apps/details?id=cx.ring)

- **开源：**✅



## 两步验证

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/18189374.png" style="zoom:6%;" /> 2FAS

支持 iOS 和安卓的免费开源身份验证器。支持创建加密备份并在设备间同步，无需帐户。

- **官网：**[2fas.com](https://2fas.com/)
- **隐私：**[tosdr.org/en/service/8201](https://tosdr.org/en/service/8201)
- **iOS：**[apps.apple.com/us/app/2fa-authenticator-2fas/id1217793794](https://apps.apple.com/us/app/2fa-authenticator-2fas/id1217793794)
- **安卓：**[https://play.google.com/store/apps/details?id=com.twofasapp](https://play.google.com/store/apps/details?id=com.twofasapp)
- **Discord：**[q4cP6qh2g5](https://discord.com/invite/q4cP6qh2g5)
- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/aegisicon.png" style="zoom:6%;" /> Aegis

安卓平台的免费开源身份验证器。具有备份/恢复功能，用户界面可定制，支持夜间模式。

- **官网：**[getaegis.app](https://getaegis.app/)
- **隐私：**[tosdr.org/en/service/4076](https://tosdr.org/en/service/4076)
- **安卓：**[https://play.google.com/store/apps/details?id=com.beemdevelopment.aegis](https://play.google.com/store/apps/details?id=com.beemdevelopment.aegis)
- **开源：**✅



## 匿名网络

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/i2plogo.png" style="zoom:15%;" /> I2P

I2P 提供了优秀的通用传输方式，很适合访问隐藏服务，并且在技术上相比 Tor 有几项明显的优势：P2P 友好，采用单向短期隧道；使用 TCP 和 UDP 的分组交换（而非电路交换） ；能够持续分析以选择性能最佳的节点。I2P 比 Tor 更去中心化，是完全分布式和自组织的，体量较小使其尚未遭遇大量封锁或拒绝服务攻击。

- **官网：**[geti2p.net](https://geti2p.net/)
- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/Freenet_logo.svg.png" style="zoom:50%;" /> Freenet

分布式匿名存储网络，支持隐私文件共享，抗审查能力强，完全点对点架构

- **官网：**[freenetproject.org](https://freenetproject.org/)
- **开源：**✅



## 笔记工具

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/24537496.png" style="zoom:14%;" /> Standard Notes

端到端加密笔记应用，支持多端同步，可通过扩展系统添加待办列表、电子表格、富文本、Markdown、数学编辑器、代码编辑器等功能，它具有内置的安全文件存储、标签/文件夹、快速搜索等功能，注重长期数据保存。

- **官网：**[standardnotes.com](https://standardnotes.com/)
- **隐私：**[tosdr.org/en/service/2116](https://tosdr.org/en/service/2116)
- **iOS：**[apps.apple.com/us/app/standard-notes/id1285392450](https://apps.apple.com/us/app/standard-notes/id1285392450)
- **安卓：**[https://play.google.com/store/apps/details?id=com.standardnotes](https://play.google.com/store/apps/details?id=com.standardnotes)
- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/256x256.png" style="zoom:13%;" /> Joplin

跨平台开源笔记应用，支持加密同步，提供 Markdown 编辑器，支持附件加密。

- **官网：**[joplinapp.org](https://joplinapp.org/)
- **隐私：**[tosdr.org/en/service/9477](https://tosdr.org/en/service/9477)
- **iOS：**[apps.apple.com/gb/app/joplin/id1315599797](https://apps.apple.com/gb/app/joplin/id1315599797)
- **安卓：**[https://play.google.com/store/apps/details?id=net.cozic.joplin](https://play.google.com/store/apps/details?id=net.cozic.joplin)
- **开源：**✅



## PGP 管理

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/org.kde.kleopatra.svg" style="zoom: 67%;" /> Kleopatra

Linux 平台的证书管理器及通用加密 GUI，支持管理 GpgSM 密钥箱中的 X.509 和 OpenPGP 证书，可从 LDAP 服务器检索证书。Windows 版本：[GPG4Win](https://www.gpg4win.org/)

- **官网：**[apps.kde.org/kleopatra](https://apps.kde.org/kleopatra)

- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/6513445.png" style="zoom:67%;" /> OpenKeychain

用于管理密钥和加密消息的安卓应用，既可单独使用，也可集成到其他应用中，如 K9-Mail、Conversations 等。

- **官网：**[openkeychain.org](https://www.openkeychain.org/)
- **隐私：**[tosdr.org/en/service/7378](https://tosdr.org/en/service/7378)
- **开源：**✅



## 元数据清理

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/exificon.svg" style="zoom:3%;" /> ExifCleaner

跨平台的高性能 EXIF 元数据清除工具，有较好的批处理支持。

- **官网：**[exifcleaner.com](https://exifcleaner.com/)
- **开源：**✅



## 搜索引擎

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/duckfavicon.png" style="zoom: 50%;" /> DuckDuckGo

不追踪用户的搜索引擎，不保存搜索记录，没有追踪器、cookie 或广告，提供 .onion 服务，有官方浏览器插件。

- **官网：**[duckduckgo.com](https://duckduckgo.com/)
- **隐私：**[tosdr.org/en/service/222](https://tosdr.org/en/service/222)
- **iOS：**[apps.apple.com/us/app/duckduckgo-private-browser/id663592361](https://apps.apple.com/us/app/duckduckgo-private-browser/id663592361)
- **安卓：**[https://play.google.com/store/apps/details?id=com.duckduckgo.mobile.android](https://play.google.com/store/apps/details?id=com.duckduckgo.mobile.android)
- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/Brave-Search-Icon.png" style="zoom:7%;" /> BraveSearch

注重隐私的搜索引擎，不追踪用户，不使用秘密算法或用户分析，基于自主搜索索引。

- **官网：**[search.brave.com](https://search.brave.com/)
- **隐私：**[tosdr.org/en/service/1487](https://tosdr.org/en/service/1487)
- **iOS：**[apps.apple.com/us/app/brave-private-browser-adblock/id1052879175](https://apps.apple.com/us/app/brave-private-browser-adblock/id1052879175)
- **安卓：**[https://play.google.com/store/apps/details?id=com.brave.browser](https://play.google.com/store/apps/details?id=com.brave.browser)
- **开源：**✅



## 浏览器插件

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/privacy-badger.png" style="zoom:6%;" /> Privacy Badger

智能追踪器检测，自动学习屏蔽，不依赖黑名单

- **官网：**[privacybadger.org](https://privacybadger.org/)
- **隐私：**[tosdr.org/en/service/682](https://tosdr.org/en/service/682)
- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/ublock.svg" style="zoom:20%;" /> uBlock Origin

屏蔽广告、追踪器和恶意网站

- **官网：**[ublockorigin.com](https://ublockorigin.com/)
- **隐私：**[tosdr.org/en/service/682](https://tosdr.org/en/service/682)
- **开源：**✅



## 匿名支付

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/getmonero.org.png" style="zoom:6%;" /> Monero

最注重隐私的加密货币，交易完全匿名，采用环签名、RingCT、Kovri 和隐秘地址等密码技术保护用户隐私。

- **官网：**[getmonero.org](https://www.getmonero.org/)
- **隐私：**[tosdr.org/en/service/8279](https://tosdr.org/en/service/8279)
- **开源：**✅

### <img src="https://fanwb.oss-cn-beijing.aliyuncs.com/img/z.cash.png" style="zoom:15%;" /> ZCash

使用零知识证明技术来保护隐私，允许用户在不泄露其真实身份或地址的情况下进行交易。 Zcash 区块链使用两种类型的地址和交易，Z 交易和地址是私有的，T 交易和地址是透明的。

- **官网：**[z.cash](https://z.cash/)
- **隐私：**[tosdr.org/en/service/8258](https://tosdr.org/en/service/8258)
- **开源：**✅

