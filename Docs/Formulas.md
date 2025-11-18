# Take-mikazuchi
## Player Version
- Additive multiplier
- Capped Takemikazuchi multiplier = Base multiplier + Exponential multiplier
- Base multiplier = $`\frac{min(hit\_rate - 100, 200)}{200}`$
- Exponential multiplier = $`\frac{1 - e^{-(\frac{hit\_rate - 300}{100})}}{2}`$
  - Applicable only when hit_rate exceeds 300%.
- Capped Takemikazuchi multiplier = $`\frac{min(hit\_rate - 100, 200)}{200}`$ + $`\frac{1 - e^{-(\frac{hit\_rate - 300}{100})}}{2}`$

## Enemy Version
- Additive multiplier
- Enemy multiplier = $`\frac{hit\_rate - 100}{100}`$
  - Normal+ and above formula
- Enemy multiplier = $`\frac{hit\_rate - 100}{200}`$
  - Normal formula

 # Revenge
 - Universal mechanic that generally boosts damage from a counterattack if a unit died when previously Support Defending an attacking unit.
 - The revenge multiplier is a additive multiplier existing in the Final Modifier damage calculation. It starts at a base value of $`+0.50`$.
 - The revenge multiplier scales with unique values that are included as part of the unit data. These unique values are mapped to specific unit_codes, so the revenge multiplier only increases if the Support Defending unit matches one of those unit_codes to give the corresponding boost.
 - These "Revenge Values" are divided by 100 and added onto the base value to give the final revenge multiplier.
 - As an example, Yukari has a Revenge Value of 65 mapped to unit_code Yuyuko. This will give a Revenge Value Boost of $`\frac{65}{100} = +0.65`$. If Yuyuko dies while Support Defending Yukari, Yukari's counterattack will be increased by a Final Modifier of $`0.65 + 0.5 = +1.15`$.
