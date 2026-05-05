# zmk-config-redoxft

Konfiguracja ZMK dla Redox FT - port z `zmk-config-cornekbh`.

## Hardware

- Shield: `redox` (oficjalny shield z upstream ZMK od PR #1002)
- Kontrolery: 2× nice!nano v2
- Wyświetlacze: 2× nice!view (po jednym na każdej połówce)
- Per-key RGB: 35 LED WS2812 na każdej połówce, data line dzielona z nice_view CS na pinie D1/TX (P0.06), tak jak w Corne i Sofle z nice!view

## Warstwy

| Numer | Nazwa | Funkcja |
|-------|-------|---------|
| 0 | DEF | QWERTY base + cyfry w górnym rzędzie |
| 1 | NAV | Strzałki, numpad, BT, F1-F10 |
| 2 | SYM | Symbole, brackets, znaki specjalne |
| 3 | ADJ | F-keys, system, bootloader, studio_unlock |
| 4 | EXTRA | Mouse emulation (ruch + kliki + scroll) |

## Build

Build odbywa się automatycznie w GitHub Actions po każdym pushu. UF2 znajdziesz w zakładce Actions → ostatni przebieg → Artifacts.

Buduje 3 firmware:
- `redox_left` - lewa połówka (central, z USB, ze studio-rpc-usb-uart)
- `redox_right` - prawa połówka (peripheral)
- `settings_reset` - do wyczyszczenia BT/ustawień, gdyby coś

## ZMK Studio

Aktywne. Lewa połówka ma `studio-rpc-usb-uart` snippet w `build.yaml`. Studio_unlock przypisany na warstwie ADJ pod F6 lewej ręki (pozycja jak `&studio_unlock` w pliku).

Po zaflashowaniu: podłącz lewą połówkę USB, otwórz [ZMK Studio](https://zmk.studio/), naciśnij studio_unlock (jeśli LOCKING jest włączone) i edytuj keymapę live.

## Mapowanie warstw vs corne

Bazowy DEF ma teraz **dostępne cyfry 1-0 bezpośrednio** w górnym rzędzie (Redox ma extra rząd numeryczny względem Corne). Reszta warstw zachowała Twoje przyzwyczajenia z Corne.

Combos zostały przeliczone na nowe pozycje klawiszy w matrycy 5×14 Redoxa - sprawdź, czy działają zgodnie z oczekiwaniami i ewentualnie dopracuj `key-positions` w `redox.keymap`.

## Dodatkowe klawisze Redoxa (28 nowych pozycji)

- **Skrajna lewa kolumna lewa**: `=`, TAB, LSHFT, LCTRL, ESC
- **Skrajna prawa kolumna prawa**: `-`, BSPC, `'`, mo EXTRA, RIGHT
- **Dodatkowy thumb cluster**: HOME/END (góra), `(`/`)` i `[`/`]` (środek), DEL/ENTER (dół)
- **Strzałki w dolnym rzędzie prawej ręki**: LEFT, DOWN, UP, RIGHT
