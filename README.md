# GenoSymb – Langage Visuel pour l’ADN

**GenoSymb** est un langage symbolique génétique basé sur des formes géométriques (▲ ▼ ○ ■) et une grammaire formelle, permettant de traduire l’ADN en un langage visuel interprétable.

Inspiré par la méthode [Lectura Vitae ∞₀](https://zenodo.org/records/15235218), le projet offre une passerelle entre séquence génétique, lecture humaine et outils bioinformatiques.

---

## 🧬 Codage Symbolique

| Base | Symbole | Couleur        | Vecteur de tension |
|------|---------|----------------|--------------------|
| A    | ▲       | Bleu `#3498DB` | [+1, 0]            |
| T    | ▼       | Rouge `#E74C3C`| [-1, 0]            |
| G    | ○       | Vert `#2ECC71` | [0, +1]            |
| C    | ■       | Jaune `#F39C12`| [0, -1]            |

---

## 📜 Grammaire BNF (symbolique)

```bnf
<génome> ::= <codon> Ⓡ <codon> Ⓡ ...
<codon>  ::= <base><base><base>
<base>   ::= ▲ | ▼ | ○ | ■
ADN     : A   T   G   C   A   T
Symbole : ▲   ▼   ○   ■   ▲   ▼
symbols = {'A': '▲', 'T': '▼', 'G': '○', 'C': '■'}

def dna_to_genosymb(sequence):
    return ''.join(symbols.get(base, '?') for base in sequence)
