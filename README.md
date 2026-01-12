# Dwains Altena Dashboard

[![Home Assistant](https://img.shields.io/badge/Home%20Assistant-2024.1+-blue.svg)](https://www.home-assistant.io/)
[![HACS](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://hacs.xyz/)
[![Version](https://img.shields.io/badge/version-3.8.2--labelfix-green.svg)](https://github.com/Adcompro/dwains-altena-dashboard/releases)

Een aangepaste versie van [Dwains Lovelace Dashboard](https://github.com/dwainscheeren/dwains-lovelace-dashboard) met verbeteringen voor mobiele weergave en thema-compatibiliteit.

![Dashboard Preview](https://raw.githubusercontent.com/dwainscheeren/dwains-lovelace-dashboard/master/.github/images/screen1.png)

---

## Wat is Dwains Dashboard?

Dwains Dashboard is een **automatisch gegenereerd Home Assistant UI dashboard** voor desktop, tablet en mobiel. Het dashboard bouwt zichzelf automatisch op basis van je Home Assistant configuratie met minimale setup.

### Kenmerken

- **Automatische generatie** - Dashboard wordt automatisch opgebouwd op basis van je Areas en Entities
- **Responsive design** - Werkt op desktop, tablet en mobiel
- **Aanpasbaar** - Voeg custom cards en blueprints toe
- **Meerdere talen** - Ondersteuning voor Nederlands, Engels, Duits, Frans, en meer
- **Thema ondersteuning** - Werkt met aangepaste Home Assistant thema's

---

## Wijzigingen in Altena versie

Deze fork bevat de volgende verbeteringen ten opzichte van de originele v3.8.0:

### v3.8.2-labelfix

#### Mobiele Layout Fix
- **Probleem:** Status badges (personen, deuren, shutters) werden verticaal onder elkaar weergegeven op mobiel
- **Oplossing:** CSS toegevoegd voor horizontale weergave met flex-wrap

#### Settings Dialog Labels Fix
- **Probleem:** Labels naast checkboxes in de instellingen dialog waren niet zichtbaar (witte tekst op witte achtergrond)
- **Oplossing:** `mwc-formfield` componenten vervangen door `<span>` elementen met expliciete inline styling

#### Thema Compatibiliteit
- Verbeterde ondersteuning voor custom thema's (zoals Light-Yellow)
- CSS conflicten opgelost voor MDC (Material Design Components)

---

## Installatie

### Methode 1: HACS (Aanbevolen)

1. Open HACS in Home Assistant
2. Ga naar **Integrations**
3. Klik op de 3 puntjes rechtsboven → **Custom repositories**
4. Voeg toe:
   - **URL:** `https://github.com/Adcompro/dwains-altena-dashboard`
   - **Category:** `Integration`
5. Zoek naar "Dwains Altena Dashboard" en installeer
6. Herstart Home Assistant

### Methode 2: Handmatige installatie

1. Download de laatste release
2. Kopieer de `dwains_dashboard` map naar `/config/custom_components/`
3. **Maak de vereiste mappen aan** (zie hieronder)
4. Herstart Home Assistant
5. Ga naar **Instellingen** → **Apparaten & Services** → **Integratie toevoegen**
6. Zoek naar "Dwains Dashboard"

### Vereiste mappen aanmaken

Dwains Dashboard verwacht bepaalde configuratie mappen. Maak deze aan als ze niet bestaan:

```bash
mkdir -p /config/dwains-dashboard/button_card_templates
mkdir -p /config/dwains-dashboard/apexcharts_card_templates
mkdir -p /config/dwains-dashboard/configs
mkdir -p /config/dwains-dashboard/blueprints
```

**Belangrijk:** Zonder deze mappen krijg je een "configuratiefout" bij het laden van het dashboard.

---

## Configuratie

Na installatie kun je het dashboard configureren via:

1. **Dashboard openen** via het zijmenu
2. **Instellingen** (tandwiel icoon) voor globale opties:
   - Klok aan/uit
   - AM/PM of 24-uurs klok
   - Welkomstbericht aan/uit
   - V2 modus (verbeterde mobiele layout)
   - Sensor grafiek aan/uit
   - Cover inverteren
   - Weer entity selecteren
   - Alarm entity selecteren

### Settings.yaml

Geavanceerde instellingen kunnen worden geconfigureerd in:
```
/config/dwains-dashboard/configs/settings.yaml
```

```yaml
alarm_entity: alarm_control_panel.alarmo
disable_clock: false
disable_welcome_message: true
v2_mode: true
weather_entity: weather.huis
am_pm_clock: false
disable_sensor_graph: false
invert_cover: false
```

---

## Vereisten

- Home Assistant **2024.1** of nieuwer
- HACS (voor eenvoudige installatie)

### Aanbevolen custom cards (via HACS)

- [Button Card](https://github.com/custom-cards/button-card)
- [Card Mod](https://github.com/thomasloven/lovelace-card-mod)
- [Auto Entities](https://github.com/thomasloven/lovelace-auto-entities)

---

## Screenshots

### Desktop weergave
Het dashboard past zich automatisch aan op basis van schermgrootte.

### Mobiele weergave
Geoptimaliseerd voor smartphones met touch-vriendelijke interface.

### Instellingen dialog
Alle opties zijn nu correct zichtbaar met leesbare labels.

---

## Ondersteuning

### Problemen melden
- [GitHub Issues](https://github.com/Adcompro/dwains-altena-dashboard/issues)

### Originele Dwains Dashboard
- [GitHub Repository](https://github.com/dwainscheeren/dwains-lovelace-dashboard)
- [Documentatie](https://dwainscheeren.github.io/dwains-lovelace-dashboard/)
- [Discord: Home Assistant Addicts](https://discord.gg/7yt64uX)

---

## Credits

### Originele ontwikkelaar
**Dwain Scheeren** - [dwainscheeren](https://github.com/dwainscheeren)
- Website: [SmartHomeShop.io](https://smarthomeshop.io)
- YouTube: [Dwain Scheeren](https://youtube.com/channel/UCb2GBaLC4d0rVn9pZbYbQ9A)

### Altena versie aanpassingen
**Adcompro** - [Adcompro](https://github.com/Adcompro)

### Met hulp van
- Claude AI (Anthropic) - Code assistentie

---

## Donaties

Als je het originele project wilt ondersteunen:
- [Buy Me a Coffee](https://www.buymeacoffee.com/dwainscheeren)
- [PayPal](https://paypal.me/dwainscheeren)

---

## Licentie

Dit project is gebaseerd op Dwains Lovelace Dashboard.

**Let op:** Het is niet toegestaan om dit dashboard door te verkopen, te herverdelen of te verkopen zonder expliciete toestemming van de originele auteur.

---

## Changelog

### v3.8.2-labelfix (2026-01-12)
- Fix: Mobiele layout badges nu horizontaal
- Fix: Settings dialog labels zichtbaar
- Fix: CSS conflicten met custom thema's
- Verbeterd: Thema compatibiliteit

### v3.8.0 (Origineel - April 2025)
- Fixes voor Home Assistant 2025.4
- Zie [originele changelog](https://github.com/dwainscheeren/dwains-lovelace-dashboard/releases)
