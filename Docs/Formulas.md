## Take-mikazuchi
# Player Version
- Capped Takemikazuchi multiplier = Base multiplier + Exponential multiplier
- Base multiplier = $`\frac{min(hit\_rate - 100, 200)}{200}`$
- Exponential multiplier = $`\frac{1 - e^{-(\frac{hit\_rate - 300}{100})}}{2}`$
  - Applicable only when hit_rate exceeds 300%.
- Capped Takemikazuchi multiplier = $`\frac{min(hit\_rate - 100, 200)}{200}`$ + $`\frac{1 - e^{-(\frac{hit\_rate - 300}{100})}}{2}`$

# Enemy Version
- Enemy multiplier = $`\frac{hit\_rate - 100}{100}`$
  - Normal+ and above formula
- Enemy multiplier = $`\frac{hit\_rate - 100}{200}`$
  - Normal formula
