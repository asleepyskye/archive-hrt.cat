---
title: Recipe Calculator
layout: home
nav_order: 5
parent: Other
permalink: /calculator
---

# Recipe Calculator

_Updated July 21, 2023_  
_Reviewed April 16, 2024_

{: .info }
Most of the raw data that was turned into this calculator can be found [here](/topics/recipes).

{: .warning }
This calculator is in beta. It uses the methodology we use to calculate our brew ratios. There may be better ways to do these calculations. Double-check the work this calculator does. Proceed with caution. Please report any information about how to improve the calculator to our git.gay page or to our email. 

<select name="recipe" id="recipe-select">
    <option value="none">--Choose a recipe--</option>
    <option value="E_PAR_20">Estradiol 20mg/mL Par Pharmaceuticals</option>
    <option value="E_PAR_40">Estradiol 40mg/mL Par Pharmaceuticals</option>
    <option value="T_SLAYBACK_200">Testosterone 200mg/mL Slayback Pharma</option>
</select>

<label for="brew-vol">Amount to brew in mL:</label>
<input type="number" id="brew-vol" name="brew-vol" value="100">

<table>
  <tr>
    <th>Ingredient</th>
    <th>Density (g/mL)</th>
    <th>Mass in 1mL</th>
    <th>Vol in 1mL</th>
    <th>Your Recipe</th>
  </tr>
  <tr>
    <td id="hormone_name">
      <select name="hormone" id="hormone-select">
        <option value="none">--Choose a hormone ester--</option>
        <option value="E">Estradiols (any)</option>
        <option value="TC">Testosterone Cypionate</option>
        <option value="TEn">Testosterone Enanthate</option>
        <option value="TU">Testosterone Undecanoate</option>
      </select>
    </td>
    <td id="hormone_density"></td>
    <td id="hormone_mass"></td>
    <td id="hormone_vol"></td>
    <td id="hormone_total"></td>
  </tr>
  <tr>
    <td>Benzyl Benzoate</td>
    <td>---</td>
    <td id="bb_mass"></td>
    <td id="bb_vol"></td>
    <td id="bb_total"></td>
  </tr>
  <tr>
    <td>Benzyl Alcohol</td>
    <td>---</td>
    <td id="ba_mass"></td>
    <td id="ba_vol"></td>
    <td id="ba_total"></td>
  </tr>
  <tr>
    <td id="oil_name">
      Carrier Oil
    </td>
    <td id="oil_density">---</td>
    <td id="oil_mass">---</td>
    <td id="oil_vol"></td>
    <td id="oil_total"></td>
  </tr>
</table>

## Technical Notes

### Ingredient Ratios:

When analyzing multiple recipes from various pharmaceutical manufacturers, a few things became clear. While the recipes are listed in mass, both BB and BA convert out into well-rounded volumetric measurements based on the density of those ingredients. For example, multiple recipes list exactly 224mg of BB per 1mL of medicine. This calculates out to be exactly 0.2mL of BB. Similar with BA. We theorize then that these ingredients are not added by weight but by volume. When you scale your recipe up, you will always see BB and BA in perfect volumetric ratios (20/40% and 2% respectively).  

For the calculator, we use the density to calculate the displacement of your hormone ester of choice. Unless you're working with ten's of liters of medicine this probably doesn't matter that much, but for the sake of accuracy this is how it's calculated.

We then look at the sum of the volume of the hormone, BB, and BA, and then fill the remaining volume with the carrier oil. 

### Rounding:
Values are rounded to the nearest 0.01, but calculations are done on the unrounded numbers.

<script src="/assets/scripts/recipe_calculator.js"/>
