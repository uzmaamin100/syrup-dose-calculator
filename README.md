# Children's Syrup Dose Calculator (study use)

A simple web app that works out a child's syrup dose from their weight.

**For study use only. Always confirm the dose with a pharmacist or doctor.**

## What it does

You type in every number from the prescription or the medicine bottle. The app only does the maths. It has no built-in drug names or doses.

**You enter:**
- Child's weight (kg)
- Dose in mg/kg **per dose**
- Number of doses per day
- Syrup strength (for example 250 mg in 5 mL)
- Maximum dose per dose in mg (optional)

**The app shows:**
- mg per dose
- mL per dose to give (rounded to 0.1 mL)
- Total mg per day
- Total mL per day
- The full working, so a pharmacist can check it

## Formula

```
mg per dose   = weight (kg) × dose (mg/kg per dose)
mL per dose   = mg per dose × (strength mL ÷ strength mg)
mg per day    = mg per dose × doses per day
mL per day    = mL per dose × doses per day
```

## Safety features

- **Maximum dose check:** if the dose is above the maximum entered, a red warning appears and the dose is capped. When capped, mL is rounded **down**, so it never goes above the maximum.
- **Weight check:** a warning appears if the weight is above 50 kg (this is a children's calculator).
- **Input checks:** friendly messages for empty boxes, zero or negative numbers.
- **No drug data inside:** doses must come from a trusted reference, such as the BNF for Children or the WHO AWaRe Antibiotic Book.

## Test examples

| Test | Weight | mg/kg per dose | Doses/day | Strength | Max | Expected result |
|---|---|---|---|---|---|---|
| Normal dose | 10 kg | 15 | 3 | 250 mg/5 mL | none | 150 mg, 3.0 mL per dose; 450 mg, 9.0 mL per day |
| Above maximum | 13 kg | 15 | 3 | 120 mg/5 mL | 187 mg | Red warning; capped 187 mg, 7.7 mL per dose |
| High weight | 60 kg | 15 | 3 | 250 mg/5 mL | none | Weight warning; 900 mg, 18.0 mL per dose |

## How to use

Open `index.html` in any web browser (Chrome, Edge). No installation needed.

## Built with

Plain HTML, CSS and JavaScript in one file, built with AI-assisted coding in Cursor.

Made by Uzma Amin, as part of the iSkills SEBT Next AI agentic coding course.
