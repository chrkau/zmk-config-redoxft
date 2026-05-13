:::writing{variant=“standard” id=“43826”}

zmk-config-redoxft

PL

Konfiguracja ZMK dla Redox FT - klawiatura ergonomiczna FalbaTech (rozszerzona).

Hardware
	•	Shield: redox (oficjalny w upstream ZMK)
	•	Kontrolery: 2× nice!nano v2
	•	Wyświetlacz: nice!view (Sharp Memory LCD)
	•	RGB: per-key WS2812, 35 LED na każdej połówce
	•	70 klawiszy (5 rzędów × 7 kolumn + 5 thumb na stronę)

Warstwy

#	Nazwa	Funkcja
0	DEF	QWERTY base
1	NAV	Strzałki, nawigacja
2	SYM	Symbole, brackets
3	ADJ	F-keys, system, BT controls
4	EXTRA	Mouse emulation + RGB controls

ZMK Studio

Aktywne. Procedura odblokowania (jednakowa we wszystkich klawiaturach FalbaTech FT):

Trzymaj oba thumby aktywujące warstwy systemowe → wciśnij skrajny lewy górny klawisz.

Po odblokowaniu klawiatura jest edytowalna z:
zmk.studio￼

Bluetooth - obsługa 5 urządzeń

Klawiatura obsługuje 5 niezależnych profili Bluetooth. W warstwie systemowej (ADJ):

Klawisz	Funkcja
Z	Profil BT 0
X	Profil BT 1
C	Profil BT 2
V	Profil BT 3
B	Profil BT 4
N	Wyczyść aktywny profil
M	Wyczyść wszystkie profile
,	Tryb USB
.	Tryb Bluetooth

Parowanie nowego urządzenia:
	1.	ADJ + odpowiedni klawisz BT (Z-B)
	2.	Znajdź “Redox FT” w liście Bluetooth na komputerze
	3.	Sparuj

RGB controls (warstwa EXTRA)

Klawisz	Funkcja
Q	RGB on/off
W	Zmiana efektu
E/R	Hue +/-
S/D	Brightness +/-
F/G	Saturation +/-
X/C	Speed +/-

Build

GitHub Actions buduje 3 firmware:
	•	redox_left-nice_nano-zmk.uf2
	•	redox_right-nice_nano-zmk.uf2
	•	settings_reset-nice_nano-zmk.uf2

Flashowanie
	1.	Lewa USB - 2× reset - przeciągnij redox_left-...uf2
	2.	Prawa USB - 2× reset - redox_right-...uf2
	3.	Połącz obie połówki przewodem TRRS
	4.	Sparuj “Redox FT” przez Bluetooth

Wsparcie

FalbaTech - https://falbatech.click

⸻

EN

ZMK configuration for Redox FT - ergonomic FalbaTech keyboard (extended version).

Hardware
	•	Shield: redox (official upstream ZMK shield)
	•	Controllers: 2× nice!nano v2
	•	Display: nice!view (Sharp Memory LCD)
	•	RGB: per-key WS2812, 35 LEDs on each half
	•	70 keys (5 rows × 7 columns + 5 thumb keys per side)

Layers

#	Name	Function
0	DEF	QWERTY base
1	NAV	Arrows, navigation
2	SYM	Symbols, brackets
3	ADJ	F-keys, system, BT controls
4	EXTRA	Mouse emulation + RGB controls

ZMK Studio

Enabled. Unlock procedure (same across all FalbaTech FT keyboards):

Hold both thumb keys activating system layers → press the top left key.

After unlocking, the keyboard can be configured from:
zmk.studio￼

Bluetooth - 5 device support

The keyboard supports 5 independent Bluetooth profiles. In the system layer (ADJ):

Key	Function
Z	BT Profile 0
X	BT Profile 1
C	BT Profile 2
V	BT Profile 3
B	BT Profile 4
N	Clear active profile
M	Clear all profiles
,	USB mode
.	Bluetooth mode

Pairing a new device:
	1.	ADJ + selected BT key (Z-B)
	2.	Find “Redox FT” in the Bluetooth device list on your computer
	3.	Pair

RGB controls (EXTRA layer)

Key	Function
Q	RGB on/off
W	Change effect
E/R	Hue +/-
S/D	Brightness +/-
F/G	Saturation +/-
X/C	Speed +/-

Build

GitHub Actions builds 3 firmware files:
	•	redox_left-nice_nano-zmk.uf2
	•	redox_right-nice_nano-zmk.uf2
	•	settings_reset-nice_nano-zmk.uf2

Flashing
	1.	Left USB - press reset 2× - drag redox_left-...uf2
	2.	Right USB - press reset 2× - drag redox_right-...uf2
	3.	Connect both halves using the TRRS cable
	4.	Pair “Redox FT” over Bluetooth

Support

FalbaTech - https://falbatech.click
:::
