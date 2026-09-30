# ID MANDAT – Standard v0.1

**Offenes Register für KI-Agenten · Open registry for AI agents**

Erstveröffentlichung / First published: 30.09.2026 · Manja König, Osnabrück · https://idmandat.com

---

## Worum es geht

Bald sprechen KI-Agenten mit KI-Agenten. Jeder Agent muss dabei zwei Fragen beantworten können:

- **ID** – Wer bist du? Welches echte Unternehmen steht hinter dir?
- **MANDAT** – Was darfst du für dieses Unternehmen tun, und was nicht?

ID MANDAT beschreibt, wie ein Unternehmen diese Fragen öffentlich und maschinenlesbar beantwortet, auf seiner eigenen Domain.

## So funktioniert es

1. **Ausweis:** Das Unternehmen legt eine Datei ab unter
   `https://<firmendomain>/.well-known/idmandat.json`
2. **DNS-Nachweis:** Ein TXT-Eintrag beweist, dass das Unternehmen die Domain kontrolliert:
   `_idmandat.<firmendomain>  TXT  "v=idmandat1; file=/.well-known/idmandat.json"`
3. **Prüfstufen:**
   - Stufe 1 – Domain: DNS-Eintrag und Datei stimmen überein (automatisch prüfbar)
   - Stufe 2 – Impressum: Name und Anschrift stimmen mit dem Impressum überein
   - Stufe 3 – Register: Der Handelsregistereintrag existiert und passt

ID MANDAT bestätigt Identität und Befugnis, **nicht** Seriosität, Qualität oder Bonität.

## Beispiel

Siehe [`idmandat-beispiel.json`](idmandat-beispiel.json).

## Felder

| Feld | Bedeutung |
|---|---|
| `organization` | Das Unternehmen, wie im Impressum und Register eingetragen |
| `agents` | Alle Agenten, die im Namen des Unternehmens handeln |
| `isHuman` | Immer `false` – ein Agent gibt sich nie als Mensch aus |
| `mandate.may` | Was der Agent tun darf |
| `mandate.mayNot` | Was ausdrücklich ausgeschlossen ist |
| `mandate.bindingOnlyAfter` | Ab wann eine Handlung verbindlich wird |
| `humanContact` | Wo ein Mensch erreichbar ist |

## Grundsätze

- Der Ausweis liegt beim Unternehmen, nicht beim Register. Er bleibt ohne ID MANDAT gültig und lesbar.
- Ein Agent gibt sich nie als Mensch aus.
- Ein Mandat nennt auch, was der Agent nicht darf.
- Kombinierbar mit A2A, MCP und Schema.org.

---

## English summary

ID MANDAT lets a company declare, on its own domain, which AI agents act on its behalf (**ID**) and what each agent may and may not do (**MANDATE**). The credential lives at `/.well-known/idmandat.json` and is bound to the domain by a DNS TXT record at `_idmandat.<domain>`. Verification levels: domain, imprint, commercial register. ID MANDAT confirms identity and authority, not trustworthiness. Field names are English so agents worldwide can read them.

## Lizenz

Dieser Standard steht unter [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.de). Jeder darf ihn nutzen und weiterentwickeln, mit Namensnennung: „ID MANDAT, Manja König, idmandat.com“.
