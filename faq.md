---
title: faq.yearn.finance
tags: "documenti, faq, pubblicato"
---

# FAQ

## Generale

### È sicuro investire denaro su Yearn?

- Fate le vostre ricerche e decidete voi stessi.

### Yearn è verificato?

- Sì, potete trovare l'elenco delle verifiche [qui](https://github.com/iearn-finance/audits).

## Feedback e Supporto

Se avete domande su come fare qualcosa, possiamo aiutarvi su:

- [Discord](http://discord.yearn.finance)
- [Telegram](https://t.me/yearnfinance)

Ma se pensate che qualcosa possa essere migliorato, o se avete trovato un bug, noi siamo qui per risolverlo. Vi preghiamo di pubblicarlo qui:

- [Github](https://github.com/iearn-finance) — crea un nuovo argomento nel relativo repository.
- [Forum](https://gov.yearn.finance/c/general-chat/feedback/2) — scrivi nella categoria feedback.

## Prodotti

### yearn.finance

- [yearn.finance](https://yearn.finance/) ospita gli UI per i prodotti **Vaults**, **Earn**, **Zap**, **APR** e **Cover**.

### Vault

- [yearn.finance/vaults](https://yearn.finance/vaults)

#### Cos'è un Vault?

- I Vault impiegano strategie per automatizzare le migliori opportunità di rendimento per l'agricoltura disponibili.
- Sono stati ideati in modo che la comunità potesse lavorare insieme per costruire nuove strategie per trovare la migliore resa.
- Andre spiega [i vault](https://medium.com/iearn/yearn-finance-v2-af2c6a6a3613) e [delegated vaults](https://medium.com/iearn/delegated-vaults-explained-fa81f1c3fce2) in questi due post.
- In poche parole, i Vault possono:
  - Usare qualsiasi attivita come liquidità..
  - Usare la liquidità come garanzia e gestire la garanzia a un livello sicuro per evitare un'inadempienza.
  - Prendere in prestito le stablecoin.
  - Impiegare le stablecoin per l'agricoltura.
  - Reinvestire le stablecoin guadagnate.

#### Non posso fare tutto questo da solo?

- Sì che puoi farlo, ma i vault ti aiutano a risparmiare sul gas, a mantenere un buon rapporto garanzie/debito per evitare le inadempienze e ottimizzare automaticamente per le strategie stablecoin a più alto rendimento, anche mentre stai dormendo.

#### Vedo il ROI sulla pagina dei vault. È quello attuale?

- No. TQuesta è la media storica per quel vault. Gli attuali APY/rendimenti non vengono mostrati come vault, sono un prodotto beta e vengono testati dal vivo.
- Vari siti di terze parti forniscono APY e altre informazioni, sono elencati qui sotto in [Statistiche](https://docs.yearn.finance/faq#statistics).

#### Quali sono i rischi?

- Mentre gli asset depositati non possono diminuire, il debito del vault può aumentare. Se una strategia non riesce a superare il debito, allora una parte del patrimonio sarà definitivamente bloccata. Se una strategia in seguito supera di nuovo il debito, l'attività sarà di nuovo disponibile a ritirarsi. Esistono meccanismi nei vault per prevenire questo, ma nulla è a prova di proiettile.
- Per ora, solo _alcuni_ Vault sono stati [controllati](https://github.com/iearn-finance/yearn-audits/blob/bdb3868c98e4fe2427898db05154942a9192efb1/MixBytes%20-%20Yearn.Finance%20protocol%20v.1%20Smart%20Contracts%20Audit%20Security%20Audit%20Report.pdf).
- Smart contract risk con qualsiasi contratto con cui i vault interagiscono.

#### Quali sono i diversi yVaults?

**yLINK e yaLINK**

- **Qual è la differenza tra i vault LINK e aLINK?**
  - Nessuna in termini di restituzioni. Il LINK depositato sarà depositato in Aave generando aLINK \(Aave interest bearing LINK\). Quindi depositando direttamente in un vault aLINK si è un passo avanti nel processo.
- **Perchè il rendimento è diverso per i vault aLINK e LINK?**
  - aLINK ha una "tassa" assicurativa dello 0,5% (che viene restituita quando viene superata). Il vault LINK non ha questa tassa per evitare la double dip.

**yETH e yWETH**

- **Qual è la differenza tra vault WETH e vault ETH?**
  - Nessuna in termini di restituzioni. L'ETH depositato sarà comunque avvolto in WETH. Il vault WETH rende solo più facile l'interazione di altri protocolli dell'Ethereum con questo vault.
- **In che modo il vault ETH si protegge dalla liquidazione?**
  - Questo vault legge il prezzo dell'ETH direttamente dal Maker's OSM \(Oracle Security Model\), un sistema che legge il prezzo Oracle con 1 ora di anticipo. Questo dà al vault 1 ora di tempo per pagare il debito del CDP prima della liquidazione. Inoltre, il vault continua ad aumentare la collateralizzazione depositando profitti ad ogni harvest call.

**Altri Vault**

- v1 Money Market vault, precedentemente chiamati iEarn, si trovano [qui](https://yearn.finance/earn).
- Altri vault si trovano [qui](https://yearn.finance/vaults).

#### Se l'attuale strategia per il vault yCRV è CRV, viene semplicemente aggiunto al mio saldo quando lo ritiro?

- No. Il vault coltivere il CRV e poi lo vendera sul mercato automaticamente. Quando si ritira si ottiene più yCRV.

#### Perché yCRV non vale \$1, é una moneta stabile, giusto?

- No, yCRV non vale \$1, e no NON é una moneta stabile. Si può pensare a yCRV come ad un indice di rendimento di stablecoin \(yDAI+yUSDC+yUSDT+yUSDT+yTUSD\) che genera anche il rendimento \(commissioni di negoziazione dal pool Curve Y). Pertanto, il prezzo di yCRV non è in diminuzione.

#### Se tolgo il mio yCRV dal vault di yCRV, questo lo riporta al pool Curve Y alla Curve, o devo fare qualcos'altro come reinvestirlo?

- Quando si ritira il proprio yCRV dal vault, si ottiene il yCRV + più gli interessi maturati - le tasse, tutto in yCRV. Dal momento che è il token yCRV che hai recuperato, è già investito nel pool di Curve Y, facendo le commissioni di swap stablecoin. Non c'è bisogno di fare altro con Curve, a meno che non vogliate investirlo [qui](https://dao.curve.fi/minter/gauges) per generare CRV.

#### Perchè non possiamo ottenere un APY migliore per il vault YFI?

- Non si possono ottenere gli stessi numeri per due monete completamente diverse. Il nuovo sBTC sta seguendo la stessa strategia del vault yCRV utilizzando il liquidity pool di Curve. La risposta ovvia è che non ci sono molte piattaforme sicure che accettano YFI come staking, quindi in questo momento non ci sono molte strategie valide per il vault YFI.

#### Ho depositato in un vault, cosa ne ricavo quando faccio un prelievo?

- È possibile ritirare solo il tipo di asset crittografato che si è inserito.
- Riceverai l'importo che hai originariamente inserito, più il rendimento che hai guadagnato, meno le spese.

#### Quali sono le tasse?

- **Tassa dello 0,5%** sui fondi prelevati dalle strategie attive
  - Ogni vault ha una parte dei fondi totali inattivi e la maggior parte di essi è attiva nella strategia. I fondi inattivi sono la differenza tra i `fondi del vault` e i `fondi della strategia`, li puoi vedere su [feel the Yearn](https://feel-the-Yearn.app/).
  - Quando ritiri, se i tuoi fondi provengono dai fondi inattivi, non ti verrà addebitata nessuna commissione di prelievo. Se provengono dalla strategia, ti verrà addebitata la tassa dello 0,5%.
- **Tassa del 5%** sul rendimento supplementare
  - Per le strategie di comunità, come il nuovo yETH vault, attualmente il 10% di questa quota va al creatore della strategia. L'altro 90% va alla tesoreria e viene poi distribuito alla governance.

#### Puoi spiegare la commissione del 5% sul rendimento aggiuntivo?

- Prima si chiamava "tassa del 5% sul gas sovvenzionato", che confondeva letteralmente tutti tranne Andre. Tecnicamente non si tratta di una tassa di performance, ma di una tassa su alcune transazioni che generano profitti e che comportano costi elevati per il gas e che sono fondamentali per il funzionamento interno del vault.
- Ogni vault ha diversi livelli. Qui ci sono due esempi che mostrano dove viene presa questa tassa quando viene richiesta la funzione `harvest()`.
- Esempio di yCRV Vault:
  - Livello 1: le stablecoin guadagnano interesse nei mercati monetari \(compound, aave, dydx\)
  - Livello 2: i token di livello 1 (yDAI, yUSDC, yUSDT e yTUSD) sono forniti come liquidity pool di yCRV per guadagnare commissioni di trading
  - Livello 3: la strategia guadagna premi in token CRV che ricicla in yCRV-**questo è l'unico livello in cui viene presa la tassa del 5%.**
-  Esempio di USDC Vault:
  - Livello 1: interesse per essere prestato a Compound
  - Livello 2: COMP liquidata a USDC
  - Livello 3: la strategia guadagna i token DF ricompensati da DForce che vengono raccolti e venduti per USDC-**questo è l'unico livello in cui viene presa la commissione del 5%.**

#### Dove vanno a finire le commissioni?

- Vanno ad una tesoreria dedicata [contratto](https://etherscan.io/address/0x93A62dA5a14C80f265DAbC077fCEE437B1a0Efde).
- Dalla tesoreria rimangono fino al limite di \$500k, oltre tale importo vengono reindirizzati alla governance [contratto](https://etherscan.io/address/0xBa37B002AbaFDd8E89a1995dA52740bbC013D992).

#### Le tasse sono sempre andate lì?

- No, quando YEARN stata avviata, le tasse andavano direttamente all'indirizzo [indirizzo](https://etherscan.io/address/0x2d407ddb06311396fe14d4b49da5f0471447d45c) di Andre..
- Poi abbiamo consegnato al [multisig](https://etherscan.io/address/0xFEB4acf3df3cDEA7399794D0869ef76A6EfAff52) e i compensi sono andati direttamente lì.
- E prima del nostro attuale gov v2, le ricompense in stake sandavano [qui](https://etherscan.io/address/0xb01419E74D8a2abb1bbAD82925b19c36C191A701)

#### Rendimento

- Abbiamo in programma di realizzare in futuro una dashboard che mostrerà chiaramente il vostra attuale APY di tutte le posizioni aperte. Attualmente per i vault, poiché sono ancora in beta, non mostriamo le APY live, ma vengono pubblicate su [twitter](https://twitter.com/iearnfinance) circa una volta al giorno. Puoi stimare approssimativamente il rendimento che stai ottenendo osservando quale [strategia attuale](https://feel-the-Yearn.vercel.app/) è l'agricoltura e verificando quale sia la sua APY.
- Per esempio, se il vault di yCRV sta coltivando il token CRV, puoi controllare qual è la resa sul sito [homepage di Curve](https://www.curve.fi/) per il pool Y

### Strategie del vault

#### Cos'è la strategia del Vault?

- Le strategie di YEARN dei vault sono smart contract modulari per ogni vault che indicano quali asset prendere in prestito, quali asset coltivare e dove vendere gli asset coltivati.

#### Quali sono le strategie attuali?

- È possibile visualizzare le strategie attuali implementate in [feel-the-Yearn](https://feel-the-Yearn.vercel.app/).
- In futuro, abbiamo in programma di creare una dashboard per rendere le strategie e l'APY facili da capire.

#### Chi ha il controllo delle strategie?

- Le scrivono gli sviluppatori, ma è il multi-sig, istruito dagli elettori YFI, a decidere se saranno implementate o meno.

#### Come posso creare una strategia?

- Per ora puoi pubblicare la tua strategia sul forum nella sezione strategie. Specificando cosa vorresti comprare/vendere/allevare e qual è l'APY attuale. Ci sarà un modello che ti aiuterò ad iniziare.

#### Qual è il processo per far arrivare la mia strategia su YEARN?

- Pubblicatela sul forum o contattate il team di sviluppo, se otterrete il supporto per la vostra idea e se finirà per essere implementata e approvata, verrà utilizzata nei vault e potrete essere pagati.

#### Quando cambia una strategia e chi la cambia? È automatica?

- I creatori di strategie osservano i mercati e scrivono strategie che ritengono sicure e che danno il massimo rendimento. Le cambiano in base ai rendimenti attuali del mercato.

### Earn

- [yearn.finance/earn](https://yearn.finance/earn)

#### Che cos'è Earn?

- Earn è un aggregatore di rendimento per piattaforme di prestito che riequilibra il rendimento più alto durante l'interazione del contratto.
- Deposita DAI, USDC, USDT, USDT, TUSD, o sUSD e presterà automaticamente al tasso di prestito più alto su queste piattaforme [Compound](https://compound.finance/), [Dydx](https://dydx.exchange/) o [Aave](https://app.aave.com/home) \(Ddex e Fulcrum sono attualmente disabilitati\).
- Per saperne di più, consulta i [Documenti Yearn](https://docs.yearn.finance/products/earn)

### Zap

- [yearn.finance/zap](https://yearn.finance/zap)

#### Che cos'è Zap?

- Zap consente agli utenti di convertire i token supportati con una sola interazione contrattuale per ridurre i costi di transazione.
- Gli Zap sono stati realizzati da DefiZap che ora è [Zapper.fi](https://zapper.fi) come un servizio di routing DeFi tutto in uno.

#### Perchè utilizzare uno Zap?

- "Gli Zap consentono di entrare in una posizione DeFi in una transazione - si chiama zapping in." - [Guida all'uso degli Zap](https://defitutorials.substack.com/p/how-to-use-defizap).
  - Si noti che questo è un vecchio articolo e che [Zapper](https://zapper.fi) è stato creato come risultato dell'unione di DeFiSnap + DeFiZap per creare l'ultimo hub per la Finanza Decentrata alias \#DeFi. Quindi alcune informazioni contenute nell'articolo di cui sopra sono obsolete, ma è ancora possibile utilizzare Zaps su Zapper.fi.

#### Allora cosa posso fare con Zaps su Yearn?

- Con uno zap puoi prendere il tuo DAI, per esempio, e ottenere yCRV in una sola transazione. Normalmente, per trasformare il DAI in yCRV, dovresti andare su Earn, depositare il DAI e ricevere yDAI, poi andare su [Curve.fi - Yearn pool](https://www.curve.fi/iearn/deposit) e depositare il tuo yDAI e poi riceverai yCRV. Questo è molto complesso, quindi invece si può fare in una sola transazione!

#### Sembra fantastico, qual è il lato negativo?

- Beh, ci vuole molto gas e potrebbe essere costoso, anche più che farlo da soli manualmente, ma se hai una transazione importante e hai fretta è un ottimo metodo per entrare velocemente in una posizione DeFi o in un liquidity pool.

### yInsure / Cover

- [yinsure.finance](https://yinsure.finance/)

#### Che cosa è yInsure?

- yInsure, noto anche come **Cover**, è un sistema di copertura in pool che fornisce un'assicurazione contro lo smart contract risk.
- Non ha nessun requisito KYC ed è sottoscritto da Nexus Mutual.
- Scopri di più in questo [articolo](https://medium.com/iearn/yinsure-finance-a-new-insurance-primitive-77d5d4217896).

### Prodotti Attualmente in Ricerca e Sviluppo

#### yTrade

- [ytrade.finance](https://ytrade.finance/)
- Negoziazioni stabili di monete con effetto leva \(testnet\).

#### yLiquidate

- [yliquidate.finance](https://yliquidate.finance/)
- 0 liquidazioni automatiche di capitale per Aave \(testnet\).

#### ySwap

- [yswap.exchange](https://yswap.exchange/)
- Market maker automatizzato su un solo lato \(testing in mainnet\).

#### yBorrow

- [yborrow.finance](https://yborrow.finance/)
- Delegazioni di credito per smart contract a smart contract \(testnet\).

## Comunicazione

- [Forum](https://gov.yearn.finance)
  -Si discute molto in tempo reale sul Telegram e su Discord, ma perché una proposta si trasformi in una YIP \(YEARN Proposta di Miglioramento\) deve essere postata e discussa sul forum.
  - Questo é il luogo principale in cui i titolari di token controllano le questioni relative alla governance.
- [Discord](http://discord.yearn.finance/)
  - Inclusi i canali non inglesi.
- [Telegram](https://t.me/yearnfinance) - Chat principale.
- [Telegram](https://t.me/yearncommunity) - Chat commerciale, sociale e di lavoro.
- Twitter
  - [yearn.finance](https://twitter.com/iearnfinance?s=20) - Twitter ufficiale di Yearn
  - [Andre Cronje](https://twitter.com/AndreCronjeTech?s=20) - Il fondatore e creatore di Yearn
  - [yLearnfinance](https://twitter.com/yLearnfinance) - Info su Yearn
  - [Learn 2 Yearn](https://twitter.com/learn2Yearn) - Info su Yearn

## Governance

### Tutto su YIPs

#### Cos'é un YIP? Perché sono importanti?

- Una proposta di miglioramento YIP o YEARN é il modo in cui le caratteristiche vengono aggiunte all'ecosistema YEARN. Gli utenti iniziano una proposta sul forum, ne discutono e valutano se la proposta sarà accettata. Se molti utenti sono d'accordo, la proposta potr essere pubblicata online per consentire a tutti di votare.

#### Quante persone devono votare per approvare una proposta YIP?

- Il quorum è del 20%. Il che significa che il 20% di YFI deve votare una proposta per farla approvare, altrimenti non verrà approvata. Inoltre, deve avere almeno il 50% dei voti per il sì.
- Puoi pubblicare prima la tua proposta, ma se la gente non ne ha parlato, probabilmente non voterà a favore.

####  Come faccio a fare una proposta?

-Il modello predefinito per le proposte può essere trovato su [Github](https://github.com/iearn-finance/YIPS/blob/master/yip-X.md) + sul [forum](https://gov.yearn.finance) se fai un post sotto proposte o discussioni, si compilerà automaticamente anche nel modello.
- Il procedimento è all'incirca il seguente:
  1. discussione sul forum
  2. promote to YIP \(usually done by mods\), add YIP to github, put on chain
  3. announce

#### Chi può fare una proposta?

- Chiunque può postare una proposta sia sul forum che online.

### Votazione

#### Come si vota?

- Mettete in stake il vostro YFI e poi potete votare per gli YIP che sono online sulla scheda di voto [cruscotto](https://ygov.finance/vote)

#### Posso votare se la mia YFI è nel vault della YFI?

- No, la tua YFI deve essere investita nella governance [contratto](https://ygov.finance/staking) per poter votare.

#### Dove posso vedere gli YIP?

- È possibile visualizzarli sulla dashboard di voto [dashboard](https://ygov.finance/vote) se si accede al proprio account web3 o a [yips.yearn.finance](https://yips.yearn.finance/all-yip).

#### Perchè dovrei partecipare? Che cos'è l'APY \(Percentuale annuale di rendimento)?

- Si dovrebbe investire se si vuole votare su YIP e ottenere ricompense che vengono generate dall'ecosistema YEARN. L'APY per lo staking non è attualmente elencata nell'IU. Puoi chiedere in chat qual è il tasso.

#### Cosa devo fare per ottenere dei premi con la mia YFI?

- Tutto quello che devi fare è puntare YFI su [ygov.finance/stake](https://ygov.finance/stake) e otterrai dei premi se la tesoreria è pari o superiore a 500k usd. Puoi controllare l'indirizzo della tesoreria [qui](https://zapper.fi/dashboard?address=0xFEB4acf3df3cDEA7399794D0869ef76A6EfAff52).
- Si noti che se si investe, si ottengono ricompense \(fintanto che non vanno alla tesoreria), ma si possono richiedere solo entro 3 giorni dal voto.

#### Lo staking della mia YFI è importante per il voto?

- Sì. Devi puntare la tua YFI su [ygov.finance/stake](https://ygov.finance/stake) nella scheda v2 sotto Governance V2 per far contare i tuoi voti. A partire da ora, potrai votare senza investire, ma sprecherai il gas e non conterà, quindi assicurati di aver investito per primo se vuoi votare.

#### Cosa succede se voglio togliere la mia YFI prima della fine del blocco del voto?

- Non si può, mi dispiace. Il blocco dura 3 giorni dopo l'ultima votazione, fino ad allora non si possono togliere i token.
- Se provi a ritirare i tuoi token prima della fine della blocco vedrai un costo del gas molto alto, questo è un errore, non potrai ritirarli fino alla fine dei 3 giorni di blocco.

#### Ho votato e so che il blocco del voto è di 3 giorni, c'è un posto dove posso vedere esattamente quanto tempo mi resta prima di poter disimpegnare la mia YFI?

- Sì! Puoi leggere il contratto direttamente su ygov.finance staking [contratto](https://etherscan.io/address/0xBa37B002AbaFDd8E89a1995dA52740bbC013D992#readContract) vai su 28 votelock e inserisci il tuo indirizzo eth. Questo ti darà il numero del blocco di eth quando potrai disimpegnare.

#### Qual è la differenza tra il voto per un sondaggio sul forum e un voto on-chain?

- Un sondaggio si limita a misurare il sentimento della community sulla proposta, mentre un voto on-chain sarà vincolante e avrà effetto se verrà approvato.

#### E il nuovo sistema di voto senza gas?

- Ora abbiamo un sistema di segnalazione off-catena che utilizza i bilanci investiti di ygov. Questo sostituisce i vecchi sondaggi informali del forum che erano vulnerabili agli attacchi di Sybil. Può fare la scelta multipla e non costa il gas da usare, si firma invece con il portafoglio. Utilizziamo ancora il normale sistema di voto on-chain per YIP.

#### Per quanto tempo è vincolato il mio YFI, se lo investo?

- Il tuo YFI è vincolato per 3 giorni dopo il voto.

#### Perchè non posso riscuotere i miei premi in stake?

- Per riscuotere i tuoi premi in stake bisogna 1\) averli investiti e 2\) aver votato entro 3 giorni per poterli riscuotere. Questo verrà stabilito a breve in un aggiornamento.

### yDAO

- Pokemol [sito](https://pokemol.com/dao/0xcb46298767fb5d44c18313976c30d3eeb5071862/).
- Forum [post](https://gov.yearn.finance/t/ydao-for-community-funding/2243).

#### Qual è il suo scopo?

- Serve a finanziare i contributi a valore aggiunto all'ecosistema Yearn.

#### Non mi importa, come faccio a guadagnarci?

- Non ci si guadagna. Questo serve solo a stanziare fondi per progetti e il YFI donato sarà speso e il valore della tua quota sarà diluito.

#### Chi può aderire?

- Aperto a chiunque possa aderire con un tasso di base di 1 azione = 0,1 YFI.

#### Come posso aderire?

- Vai qui per [Pokemol](https://pokemol.com/dao/0xcb46298767fb5d44c18313976c30d3eeb5071862) accedi con il tuo account web3. Clicca sul pulsante Nuova Proposta in alto a destra. Clicca su membro.
  - Titolo: il tuo nome/entità
  - Descrizione: "Offerta di garanzia di un importo X di YFI in cambio di azioni Y" \(Si prega di renderlo coerente con l'importo in stake a 0,1 YFI per azione)
  - Link: Link a te o alla tua entità \(Sito web, Twitter, Linkedin\)
  - Azioni richieste: Il numero di Azioni richieste
  - Tributo con token: La quantità di YFI che è stata promessa in stake \(dovrai sbloccare YFI)
  - Il bottino: Il numero di azioni richieste
  - Dopo che avrai inviato le due transazioni e che ti troverai nella coda dei nuovi membri, avrai bisogno di uno sponsor. Ti preghiamo di copiare il link alla tua proposta e di farci sapere che intendi unirti al [canale Telegram yDAO](https://t.me/joinchat/Qn1GPBv0y7lY1vAmRCB7KA)

#### Come posso richiedere un finanziamento?

- Come per l'adesione, ma invece di cliccare su membro, clicca sulla scheda di finanziamento e compila i dettagli della tua richiesta. Potete chiedere nella [chat telegram](https://t.me/joinchat/Qn1GPBv0y7lY1vAmRCB7KA) se avete domande.

#### Non parlo inglese, quando sarò tradotto il tutto?

- Stiamo lavorando per tradurre in altre lingue, ma ci vorrà del tempo. Per ora potete cliccare sulla vostra lingua nella sezione globale in [Discord](http://discord.yearn.finance/).

## Community

### Yearn ha un manifesto?

- Alcuni collaboratori si sono riuniti e hanno scritto un post su come pensano al protocollo, mentre altri si sono uniti per sostenerlo. È disponibile [sul forum](https://gov.yearn.finance/t/how-we-think-about-yearn/).

### Andre Cronje è il responsabile di Yearn?

- Andre non è responsabile di Yearn, i titolari del token YFI prendono le decisioni su come governare Yearn, Andre è uno degli sviluppatori dell'ecosistema YEARN.

### Cos'è il multisig e cosa fanno?

- L'indirizzo multisig è spiegato in dettaglio in questos [thread](https://gov.yearn.finance/t/yfi-minting-ownership/155). Fondamentalmente, è un account multisig 6 di 9 multisig che ha il controllo sul conio di YFI se un voto per coniare gettoni è passato con successo.

### Chi sono i 9 firmatari multisig?

- [Cp0x.com](https://twitter.com/kaplansky1/status/1285427247286046725)
- [Daryllautk](https://twitter.com/Daryllautk/status/1285434908383444992)
- [Devops199fan](https://twitter.com/devops199fan/status/1285430347954622464)
- [Banteg](https://twitter.com/bantg/status/1285426492906909696)
- [Milkyklim](https://milkyklim.keybase.pub/yearn-social-proof.txt)
- [Joe Mahon aka Substreight](https://twitter.com/Substreight/status/1299780260737630209)
- [Tarun Chitra, Gauntlet](https://twitter.com/gauntletnetwork/status/1299778153674616833)
- [Vasiliy Shapovalov, p2p.org](https://twitter.com/_vshapovalov/status/1299799139635679232)
- [Mariano Conti, ex-MakerDAO](https://twitter.com/nanexcool)

### I firmatari multisig sono cambiati?

- Sì, [YIP-40](https://gov.yearn.finance/t/yip-40-replace-inactive-multisig-signers/3535) ha cambiato quattro dei firmatari
- I firmatari uscenti erano:
  - [Coopahtroopa](https://twitter.com/Cooopahtroopa/status/1285438650550038529)
  - [Michael, Curve.fi](https://twitter.com/CurveFinance/status/1285428322986389504)
  - [Calvin Liu](https://twitter.com/cjliu49/status/1285439553180798976)
  - [Damir Bandalo](https://twitter.com/damirbandalo/status/1285500362015875073)

### Quali decisioni può prendere Andre da solo?

- Andre può costruire l'ecosistema YEARN e proporre nuovi prodotti. Di solito, pubblica i suoi pensieri e le sue idee sul [forum](https://gov.yearn.finance) o sul suo [blog medium](https://andrecronje.medium.com) affinché tutti possano vederli.

### Il gruppo multisig gli dice cosa fare?

- Sono in stretto contatto tra loro, ma le priorità di Andre sono le sue. Possono essere istruiti tramite YIPs.

### Chi altro scrive il codice per YEARN? C'è un team?

- Sì! Conosci alcuni degli sviluppatori di Yearn:

  - [@banteg](https://gov.yearn.finance/u/banteg)
  - [@fubuloubu](https://gov.yearn.finance/u/fubuloubu)
  - [@x48](https://gov.yearn.finance/u/x48)
  - [@doug](https://gov.yearn.finance/u/doug)
  - [@luciano](https://gov.yearn.finance/u/luciano)
  - [@orbxball](https://gov.yearn.finance/u/orbxball)

### Qualcuno viene pagato per lavorare su Yearn?

- Sì. Yearn ha un core team che riceve pagamenti ricorrenti. Le sovvenzioni vengono anche distribuite mensilmente ai collaboratori più importanti. Per esempio, si veda il [Annuncio delle sovvenzioni di settembre](https://gov.yearn.finance/t/september-grants-announcement/7044).

### Come posso lavorare per Yearn?

- Se vuoi contribuire anche tu al progetto, contatta i nostri community manager su [Discord](http://discord.yearn.finance/)/[Telegram](https://t.me/yearnfinance)/[Twitter](https://twitter.com/iearnfinance). Presto pubblicheremo anche una Guida per i contributori.

### C'è qualche posizione aperta?

- Sì! Abbiamo bisogno di tutti i tipi di profili per contribuire a rendere l'ecosistema YEARN un prodotto fiorente e per dare valore a YFI. Puoi chiedere su Discord o su Telegram di candidarti o postare sul forum. Dicci come pensi di poter aggiungere valore a YEARN e quanto pensi di dover essere pagato dal pool della community. Inoltre, puoi anche andare al [yDAO](https://gov.yearn.finance/t/ydao-for-community-funding/2243) per un finanziamento sul tuo lavoro per l'ecosistema Yearn.

### ome partecipare?

- Puoi partecipare a YFI votando gli YIP attivi, discutendo gli YIP ancora da proporre sui forum e parlando di YFI su Telegram e su Discord. Se sai una seconda lingua aiutaci a tradurre il sito e gli YIPs in quella lingua.

### Sforzi continui per migliorare l'ecosistema Yearn

- È possibile visualizzare gli YIP attivi [qui](https://yips.yearn.finance/all-yip)

## Interfaccia utente

### Posso usare le dApp dell'ecosistema Yearn sul mio telefono?

- Sì, è necessario utilizzare il browser Metamask

## Supporto tecnico

### Ho inviato la mia transazione ETH ma dice in sospeso?. Come posso risolvere il problema?

- Se si desidera che una transazione avvenga rapidamente, è necessario impostare il gas in modo corretto. Controllate i prezzi attuali del gas su [Ethgasstation](https://ethgasstation.info/) o [gasnow](https://www.gasnow.org/).
- Se usate MetaMask e fate passare la vostra transazione ma sta andando troppo lentamente, avete la possibilità di velocizzarla cliccando il pulsante velocizza sotto la vostra ultima transazione in sospeso sotto "attività". Questo dovrebbe rispedire lo stesso TX di nuovo con un prezzo del gas più alto per farlo confermare più velocemente.
- Se avete provato tutto e la vostra transazione è ancora bloccata in sospeso, potete sistemarla inviando una transazione al nonce della prima transazione bloccata con un prezzo del gas elevato per sovrascrivere la coda bloccata. Ecco una buona [guida](https://ethgasstation.info/blog/stuck-transaction-guide) che spiega come farlo.

### Perchè la tassa di prelievo è così alta?

- Se le tariffe sono più alte del normale mentre si utilizza l'ecosistema YEARN, allora può essere dovuto alla congestione dell'Ethereum e a costi del gas anormalmente elevati. Controllare [Ethgasstation](https://ethgasstation.info/). Le vostre opzioni sono di aspettare che i prezzi del gas scendano o di spendere il denaro per elaborare la vostra transazione ora.
- Se i prezzi del gas sono follemente alti, significa che c'è un errore e la transazione non potrà essere elaborata. Ad esempio, se state cercando di depositare un token che non avete o se non c'è una copertura disponibile per un contratto a [http://yinsure.finance/](http://yinsure.finance/).

## Progetti correlati

### [Curve](https://www.curve.fi)

- urve è un liquidity pool di scambio sull'Ethereum \(come [Uniswap](https://app.uniswap.org/#/)\) progettato per \(1\) il trading di stablecoin estremamente efficiente \(2\) a basso rischio, entrate da commissioni supplementari per i fornitori di liquidità, senza costi di opportunità. Curve permette agli utenti \(e contratti intelligenti come 1inch, Paraswap, Totle e Dex.ag\) di operare tra DAI e USDC con un algoritmo a basso slittamento e a bassa commissione progettato appositamente per stablecoin e per guadagnare commissioni. Dietro le quinte, il liquidity pool viene fornito anche al protocollo Compound o YEARN.finance, dove genera un reddito ancora maggiore per i fornitori di liquidità.
- Curve [FAQ](https://www.curve.fi/rootfaq).

### [Aave](https://app.aave.com/home)

-  Aave è un protocollo open source e non detentivo che consente la creazione di mercati monetari. Gli utenti possono guadagnare interessi sui depositi e prendere in prestito asset.

## Risorse

### Dove posso saperne di più su Yearn?

- [Learn Yearn](https://www.learnyearn.finance/)
- [Medium.com/iearn](https://medium.com/iearn)
- [yCosystem](https://ycosystem.info/)

### Elenchi di smart contract

- [https://gov.yearn.finance/t/yearn-contracts/1951](https://gov.yearn.finance/t/yearn-contracts/1951)
- [https://etherscan.io/accounts/label/yearn-finance](https://etherscan.io/accounts/label/yearn-finance)
  - sign-in required
- [Delegated controller](https://etherscan.io/address/0x2be5d998c95de70d9a38b3d78e49751f10f9e88b#readContract)
- [StrategyVaultTUSD](https://etherscan.io/address/0x35CEE4c61B7619956e0B2015B5411F93CBba817A#code)
- [yLINK token](https://etherscan.io/address/0x881b06da56bb5675c54e4ed311c21e54c5025298#code)
- [yaLINK token](https://etherscan.io/address/0x29e240cfd7946ba20895a7a02edb25c210f9f324#readContract)
- [StrategyMStableSavingsTUSD](https://etherscan.io/address/0xd6214317bf66921154d78e3074bada013a4de8e8#readContract)
- [yTUSD](https://etherscan.io/address/0x37d19d1c4e1fa9dc47bd1ea12f742a0887eda74a)
- [yTokenRebalance](https://etherscan.io/address/0x19b6424C58aFcee6D0cb954D4B8d44B9b5e9cC09#code)
- [CollateralVaultProxy](https://etherscan.io/address/0xf0988322b8392245d6232e520bf3cdf912b043c4)
- [USDC strategy for LINK](https://etherscan.io/address/0x25fAcA21dd2Ad7eDB3a027d543e617496820d8d6)
- [Strategy for USDC vault](https://etherscan.io/address/0xA30d1D98C502378ad61Fe71BcDc3a808CF60b897)
- [Strategy for USDC vault](https://etherscan.io/address/0xA30d1D98C502378ad61Fe71BcDc3a808CF60b897)
- [DAI vault](https://etherscan.io/address/0xACd43E627e64355f1861cEC6d3a6688B31a6F952)

### Registro dei token e dei contratti di utilità

- [https://docs.yearn.finance/developers/deployed-contracts-registry](https://docs.yearn.finance/developers/deployed-contracts-registry)

### Riferimento dettaglio Vault

- [https://vaults.finance/](https://vaults.finance/)

### Statistiche

- [yieldfarming.info](https://yieldfarming.info/)
- [yVault ROI Calculator](https://py-earn.herokuapp.com/)
- [stats.finance/yearn](https://stats.finance/yearn)
- [Feel The Yearn](https://feel-the-yearn.vercel.app/)
- Distribuzione iniziale [Dune Dashboard](https://explore.duneanalytics.com/dashboard/yearn)
- Statistiche di voto [Dune Dashboard](https://explore.duneanalytics.com/public/dashboards/Lqnxzm7fa8NVhKC4kc37DDFPZgqXryaIjyLRYAYp)
- Statistiche dei Vault [Dune Dashboard](https://explore.duneanalytics.com/public/dashboards/g0bGfgloeXBd9C18jpBjdXi5KkQjR7IXYqFRUnHk)

### Ultime notizie da Yearn

- [yearn.finance](https://twitter.com/iearnfinance) - Twitter ufficiale di Yearn
- [AndreCronjeTech](https://twitter.com/AndreCronjeTech)
- [Yearn Finance](https://medium.com/iearn) - Blog ufficiale

### Podcast

- [Unchained - Andre Cronje su YFI e sul lancio equo: 'Sono pigro'](https://unchainedpodcast.com/andre-cronje-of-yearn-finance-on-yfi-and-the-fair-launch-im-lazy/)
- [Andre Cronje e la filosofia della Finanza di Yearn](https://anchor.fm/hasu-research/episodes/6-Andre-Cronje-and-the-Philosophy-of-Yearn-Finance-ei4vds)
- [Il podcast di FTX - Andre Cronje, Architetto DeFI](https://open.spotify.com/episode/6d14TJtQU7eB69azelpdeh)
- [Chiamata della comunità Zapper - Con Andre](https://www.youtube.com/watch?v=venoiaiVZ-U)
- [SU DeFi My Money e attualmente mio. È un concetto bellissimo, ma ha delle responsabilità - Andre Cronje](https://anchor.fm/camila-russo/episodes/In-DeFi-My-Money-is-Actually-Mine--Its-a-Beautiful-Concept-But-it-Comes-With-Responsibilities-Andre-Cronje-ehs3op)
- [YFI: Coltivare gli agricoltori\| Andre Cronje](http://podcast.banklesshq.com/25-king-of-the-yield-farmers-andre-cronje)

### Blogs

- [Yearn Finance - Blog ufficiale](https://medium.com/iearn)
  - [Yinsure.finance: Un nuovo primitivo assicurativo](https://medium.com/iearn/yinsure-finance-a-new-insurance-primitive-77d5d4217896)
  - [Vault delegati spiegati](https://medium.com/iearn/delegated-vaults-explained-fa81f1c3fce2)
  - [yearn.finance v2](https://medium.com/iearn/yearn-finance-v2-af2c6a6a3613?source=---------3------------------)
  - [Forum sulla governance di Yearn](https://medium.com/iearn/yearn-governance-forum-7b7c9d0300ac?source=collection_home---6------2-----------------------)
  - [YFI premia il pool di ricompense](https://medium.com/iearn/yfi-rewards-pool-810ef9256ec6)
  - [YFI](https://medium.com/iearn/yfi-df84573db81)

### Loghi

- Può essere trovato su Discord qui sotto [\#media-resources](https://discord.com/channels/734804446353031319/736132884443955242/740325105904779326)
