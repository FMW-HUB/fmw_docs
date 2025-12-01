# 1. Data_Skills.txt
1. Create a new row with the requisite fields for your new PS. The easiest way to start can by copying another PS to clone it.
   Using the Udonge Sniper PS as an example, the following image shows what the format should look like. It is shortened for clarity, but the whole row should be copied.
   
   ![image1](/Docs/Tutorials/Tutorial_Images/udonge_PS.png)

3. Change the 2nd column ID value to whatever new unique ID the new PS will have.
   Renamed DAM+_SPIRIT_UDONGE to DAM+_SPIRIT_NITORI for the new Sniper PS on Nitori.
   
   ![image1](/Docs/Tutorials/Tutorial_Images/nitori_PS.png)

# 2. data_char_skill_all.txt
  `data_char_skill_all.txt` controls when PSes should be learned by level for each character version.
  1. Insert a new row that contains info for your new PS to add by level up. You'll need to find the character unit version you want to add to for the 1st column, the 2nd column is your new unique ID to give your new PS, and the 3rd column and beyond are the levels at which the character will learn the PS (each column thereafter corresponds to a skill level if the PS has multiple skill levels). If you want to play it safe, you can duplicate the new row and add the PS to all character versions you want the PS to be available to.

I want to add the new PS, so I create a new row. Then I find character version `Nitori04` and add my unique ID DAM+_SPIRIT_NITORI ID to that row, and since this is not a PS that levels up, I just set the 3rd column to 1 so that `Nitori04` already gets the PS at level 1. 

This should automatically update the character regardless of saves; the game will just read the `data_char_skill_all.txt` file to find all PSes that a character learns and rebuild the PS skill set depending on the current level of the character in a save.

Before:

![image1](/Docs/Tutorials/Tutorial_Images/nitori04_PS_levels.png)

After:

![image1](/Docs/Tutorials/Tutorial_Images/nitori04_PS_levels_after.png)

If all goes well, you'll see `Nitori04` getting the new PS upon loading your saves

![image1](/Docs/Tutorials/Tutorial_Images/Nitori_PS_set.png)
