# OKLCH über Weiß (Variante a)

Ziel: Für gegebene sRGB-Hex-Farben transparente OKLCH-Farben ermitteln, so dass die Komposition über Weiß (#fff) exakt die Originalfarbe ergibt – und zwar mit minimalem Alpha je Farbe (Variante a).

Formeln (linear-sRGB):
- Gegeben Ziel T (linear sRGB).
- Minimales Alpha: a = 1 − min(T_r, T_g, T_b).
- Quellfarbe X (die "eigentliche" Farbe mit Alpha a): X = 1 − (1 − T)/a.
- Ergebnis wird als `oklch(L% C h / A%)` ausgegeben.
- Rundung: L zwei Nachkommastellen (Prozent), C drei, h zwei, Alpha ganze Prozent.

Ablauf:
1) `npm ci`
2) `npm run build` erzeugt `dist/colors.oklch.css` mit allen Variablen.

Technik:
- Farbraum-Konvertierungen via colorjs.io (CSS Color 4, D65).
- Rechnung in linear-sRGB, Ausgabe in OKLCH.

Lizenz: MIT