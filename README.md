# Roll20 Macros

A few macros I use to enhance my Roll 20 experience.

## Notes

I dont have the links to the authors of these, will try and fill out for credit later.
Some of these have HTML codes in them that do not react well if you go back into the macro in roll20 - upon opening it the second time it does something to the HTML codes and breaks the macro.  If you need to edit, edit in a text editor and make every update a fresh copy. (Issue as of 03/08/2018)


# One click Initiatve

**Effect:**  Token action button for one click initiative - click token, click initiative button.

Copy as a new macro, ensure 'Show as Token Action' is selected


```
%{selected|npc_init}
```

# Ability check

**Effect:** Token action button to present dropdown menu.  Presents a easy to access menu to roll an ability check for a character.

Copy as a new macro, ensure 'Show as Token Action' is selected.  Select token and then select button.

```
@{selected|wtype}&{template:default} {{name=Ability Score for @{selected|character_name}}} {{?{Ability Score
  | Strength, Strength +@{selected|strength_mod}@{selected|jack_bonus}=[[@{selected|d20}+@{selected|strength_mod}@{selected|jack_bonus}]] - [[@{selected|d20}+@{selected|strength_mod}@{selected|jack_bonus}]]
  | Dexterity, Dexterity +@{selected|dexterity_mod}@{selected|jack_bonus}=[[@{selected|d20}+@{selected|dexterity_mod}@{selected|jack_bonus}]] - [[@{selected|d20}+@{selected|dexterity_mod}@{selected|jack_bonus}]]
  | Constitution, Constitution +@{selected|constitution_mod}@{selected|jack_bonus}=[[@{selected|d20}+@{selected|constitution_mod}@{selected|jack_bonus}]] - [[@{selected|d20}+@{selected|constitution_mod}@{selected|jack_bonus}]]
  | Intelligence, Intelligence +@{selected|intelligence_mod}@{selected|jack_bonus}=[[@{selected|d20}+@{selected|intelligence_mod}@{selected|jack_bonus}]] - [[@{selected|d20}+@{selected|intelligence_mod}@{selected|jack_bonus}]]
  | Wisdom, Wisdom +@{selected|wisdom_mod}@{selected|jack_bonus}=[[@{selected|d20}+@{selected|wisdom_mod}@{selected|jack_bonus}]] - [[@{selected|d20}+@{selected|wisdom_mod}@{selected|jack_bonus}]]
  | Charisma, Charisma +@{selected|charisma_mod}@{selected|jack_bonus}=[[@{selected|d20}+@{selected|charisma_mod}@{selected|jack_bonus}]] - [[@{selected|d20}+@{selected|charisma_mod}@{selected|jack_bonus}]]
}}}
```

# Skill Check


```
@{selected|wtype}&{template:simple} @{selected|rtype}?{Skill
|Acrobatics,+[[(@{selected|acrobatics_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_acrobatics}*@{selected|npc})]][ACRO] ]]}} {{rname=^{acrobatics-u}}} {{mod=[[ [[(@{selected|acrobatics_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_acrobatics}*@{selected|npc})]][ACRO] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|acrobatics_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_acrobatics}*@{selected|npc})]][ACRO] ]]
|Animal Handling,+[[(@{selected|animal_handling_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_animal_handling}*@{selected|npc})]][ANIM] ]]}} {{rname=^{animal-handling-u}}}{{mod=[[ (@{selected|animal_handling_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_animal_handling}*@{selected|npc})]][ANIM] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|animal_handling_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_animal_handling}*@{selected|npc})]][ANIM] ]]
|Arcana,+[[(@{selected|arcana_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_arcana}*@{selected|npc})]][ARC] ]]}} {{rname=^{arcana-u}}} {{mod=[[ [[(@{selected|arcana_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_arcana}*@{selected|npc})]][ARCA] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|arcana_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_arcana}*@{selected|npc})]][ARCA] ]]
|Athletics,+[[(@{selected|athletics_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_athletics}*@{selected|npc})]][ARC] ]]}} {{rname=^{athletics-u}}} {{mod=[[ [[(@{selected|athletics_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_athletics}*@{selected|npc})]][ATHL] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|athletics_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_athletics}*@{selected|npc})]][ATHL] ]]
|Decpetion,+[[(@{selected|deception_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_deception}*@{selected|npc})]][ARC] ]]}} {{rname=^{deception-u}}} {{mod=[[ [[(@{selected|deception_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_deception}*@{selected|npc})]][DECE] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|deception_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_deception}*@{selected|npc})]][DECE] ]]
|History,+[[(@{selected|history_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_history}*@{selected|npc})]][ARC] ]]}} {{rname=^{history-u}}} {{mod=[[ [[(@{selected|history_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_history}*@{selected|npc})]][HIST] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|history_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_history}*@{selected|npc})]][HIST] ]]
|Insight,+[[(@{selected|insight_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_insight}*@{selected|npc})]][ARC] ]]}} {{rname=^{insight-u}}} {{mod=[[ [[(@{selected|insight_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_insight}*@{selected|npc})]][INSI] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|insight_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_insight}*@{selected|npc})]][INSI] ]]
|Intimidation,+[[(@{selected|intimidation_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_intimidation}*@{selected|npc})]][ARC] ]]}} {{rname=^{intimidation-u}}} {{mod=[[ [[(@{selected|intimidation_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_intimidation}*@{selected|npc})]][INTI] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|intimidation_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_intimidation}*@{selected|npc})]][INTI] ]]
|Investigation,+[[(@{selected|investigation_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_investigation}*@{selected|npc})]][ARC] ]]}} {{rname=^{investigation-u}}} {{mod=[[ [[(@{selected|investigation_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_investigation}*@{selected|npc})]][INVE] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|investigation_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_investigation}*@{selected|npc})]][INVE] ]]
|Medicine,+[[(@{selected|medicine_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_medicine}*@{selected|npc})]][ARC] ]]}} {{rname=^{medicine-u}}} {{mod=[[ [[(@{selected|medicine_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_medicine}*@{selected|npc})]][MEDI] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|medicine_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_medicine}*@{selected|npc})]][MEDI] ]]
|Nature,+[[(@{selected|nature_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_nature}*@{selected|npc})]][ARC] ]]}} {{rname=^{nature-u}}} {{mod=[[ [[(@{selected|nature_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_nature}*@{selected|npc})]][NATU] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|nature_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_nature}*@{selected|npc})]][NATU] ]]
|Perception,+[[(@{selected|perception_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_perception}*@{selected|npc})]][ARC] ]]}} {{rname=^{perception-u}}} {{mod=[[ [[(@{selected|perception_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_perception}*@{selected|npc})]][PERC] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|perception_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_perception}*@{selected|npc})]][PERC] ]]
|Performance,+[[(@{selected|performance_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_performance}*@{selected|npc})]][ARC] ]]}} {{rname=^{performance-u}}} {{mod=[[ [[(@{selected|performance_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_performance}*@{selected|npc})]][PERF] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|performance_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_performance}*@{selected|npc})]][PERF] ]]
|Persuasion,+[[(@{selected|persuasion_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_persuasion}*@{selected|npc})]][ARC] ]]}} {{rname=^{persuasion-u}}} {{mod=[[ [[(@{selected|persuasion_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_persuasion}*@{selected|npc})]][PERS] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|persuasion_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_persuasion}*@{selected|npc})]][PERS] ]]
|Religion,+[[(@{selected|religion_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_religion}*@{selected|npc})]][ARC] ]]}} {{rname=^{religion-u}}} {{mod=[[ [[(@{selected|religion_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_religion}*@{selected|npc})]][RELI] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|religion_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_religion}*@{selected|npc})]][RELI] ]]
|Sleight of Hand,+[[(@{selected|sleight_of_hand_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_sleight_of_hand}*@{selected|npc})]][ARC] ]]}} {{rname=^{sleight_of_hand-u}}} {{mod=[[ [[(@{selected|sleight_of_hand_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_sleight_of_hand}*@{selected|npc})]][SLEI] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|sleight_of_hand_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_sleight_of_hand}*@{selected|npc})]][SLEI] ]]
|Stealth,+[[(@{selected|stealth_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_stealth}*@{selected|npc})]][ARC] ]]}} {{rname=^{stealth-u}}} {{mod=[[ [[(@{selected|stealth_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_stealth}*@{selected|npc})]][STEA] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|stealth_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_stealth}*@{selected|npc})]][STEA] ]]
|Survival,+[[(@{selected|survival_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_survival}*@{selected|npc})]][ARC] ]]}} {{rname=^{survival-u}}} {{mod=[[ [[(@{selected|survival_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_survival}*@{selected|npc})]][SURV] ]]}} {{r1=[[@{selected|d20}+[[(@{selected|survival_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.00001)))+(@{selected|npc_survival}*@{selected|npc})]][SURV] ]]
}}} @{selected|global_skill_mod} @{selected|charname_output}
```
# Whisper save list

**Effect:** Whisper the selected character a list of saves, abilitie checks and their tool.

``
/w "@{selected|character_name}" &{template:atk} {{desc=**Saving Throws**
[Strength](~Selected|strength_save) **|** [Dexterity](~Selected|dexterity_save) **|** [Constitution](~Selected|constitution_save)
[Intelligence](~Selected|intelligence_save) **|** [Wisdom](~Selected|wisdom_save) **|** [Charisma](~Selected|charisma_save)
**-----------------------------------------------**
**Ability Checks**
[Strength](~Selected|strength) **|** [Dexterity](~Selected|dexterity) **|** [Constitution](~Selected|constitution)
[Intelligence](~Selected|intelligence) **|** [Wisdom](~Selected|wisdom) **|** [Charisma](~Selected|charisma)
**-----------------------------------------------**
**Physical Skills**
[Acrobatics](~Selected|acrobatics) **|** [Athletics](~Selected|athletics) **|** [Steath](~Selected|stealth)
**Social Skills**
[Persuasion](~Selected|persuasion) **|** [Deception](~Selected|deception) **|** [Insight](~Selected|insight)
[Intimidation](~Selected|intimidation)
**Senses**
[Investigation](~Selected|investigation) **|** [Perception](~Selected|perception)
**Knowledge**
[Arcana](~Selected|arcana) **|** [History](~Selected|history) **|** [Medicine](~Selected|medicine)
[Nature](~Selected|nature) **|** [Religion](~Selected|religion)
**Miscellaneous**
[Survival](~Selected|survival) **|** [Animal Handling](~Selected|animal_handling)
[Performance](~Selected|performance) **|** [Sleight of Hand](~Selected|sleight_of_hand)
**-----------------------------------------------**
**Tools**
[@{Selected|repeating_tool_$0_toolname}](~Selected|repeating_tool_$0_tool)
}}
``

# Spellbook (WIP)

**Effect:** A macro to whisper a character their spellbook, including icons for prepared spells.
Needs customization per character to the size of their spellbook unfortuantly.

```
/w "@{selected|character_name}"&{template:atk} {{desc=**Cantrips**
[@{Selected|repeating_spell-cantrip_$0_spellname}](~Selected|repeating_spell-cantrip_$0_spell)
[@{Selected|repeating_spell-cantrip_$1_spellname}](~Selected|repeating_spell-cantrip_$1_spell)
[@{Selected|repeating_spell-cantrip_$3_spellname}](~Selected|repeating_spell-cantrip_$3_spell)
[@{Selected|repeating_spell-cantrip_$4_spellname}](~Selected|repeating_spell-cantrip_$4_spell)
[@{Selected|repeating_spell-cantrip_$5_spellname}](~Selected|repeating_spell-cantrip_$5_spell)
[@{Selected|repeating_spell-cantrip_$6_spellname}](~Selected|repeating_spell-cantrip_$6_spell)

** 1st Level **
[@{Selected|repeating_spell-1_$0_spellname}](~Selected|repeating_spell-1_$0_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$0_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$1_spellname}](~Selected|repeating_spell-1_$1_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$1_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$2_spellname}](~Selected|repeating_spell-1_$2_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$2_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$3_spellname}](~Selected|repeating_spell-1_$3_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$3_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$4_spellname}](~Selected|repeating_spell-1_$4_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$4_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$5_spellname}](~Selected|repeating_spell-1_$5_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$5_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$6_spellname}](~Selected|repeating_spell-1_$6_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$6_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$7_spellname}](~Selected|repeating_spell-1_$7_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$7_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$8_spellname}](~Selected|repeating_spell-1_$8_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$8_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$9_spellname}](~Selected|repeating_spell-1_$9_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$9_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$10_spellname}](~Selected|repeating_spell-1_$10_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$10_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$11_spellname}](~Selected|repeating_spell-1_$11_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$11_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$12_spellname}](~Selected|repeating_spell-1_$12_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$12_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$13_spellname}](~Selected|repeating_spell-1_$13_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$13_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$14_spellname}](~Selected|repeating_spell-1_$14_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$14_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$15_spellname}](~Selected|repeating_spell-1_$15_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$15_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$16_spellname}](~Selected|repeating_spell-1_$16_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$16_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$17_spellname}](~Selected|repeating_spell-1_$17_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$17_spellprepared}#.jpg) 
[@{Selected|repeating_spell-1_$18_spellname}](~Selected|repeating_spell-1_$18_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-1_$18_spellprepared}#.jpg) 


** 2st Level **
[@{Selected|repeating_spell-2_$0_spellname}](~Selected|repeating_spell-2_$0_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$0_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$1_spellname}](~Selected|repeating_spell-2_$1_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$1_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$2_spellname}](~Selected|repeating_spell-2_$2_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$2_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$3_spellname}](~Selected|repeating_spell-2_$3_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$3_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$4_spellname}](~Selected|repeating_spell-2_$4_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$4_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$5_spellname}](~Selected|repeating_spell-2_$5_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$5_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$6_spellname}](~Selected|repeating_spell-2_$6_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$6_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$7_spellname}](~Selected|repeating_spell-2_$7_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$7_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$8_spellname}](~Selected|repeating_spell-2_$8_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$8_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$9_spellname}](~Selected|repeating_spell-2_$9_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$9_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$10_spellname}](~Selected|repeating_spell-2_$10_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$10_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$11_spellname}](~Selected|repeating_spell-2_$11_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$11_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$12_spellname}](~Selected|repeating_spell-2_$12_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$12_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$13_spellname}](~Selected|repeating_spell-2_$13_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$13_spellprepared}#.jpg) 
[@{Selected|repeating_spell-2_$14_spellname}](~Selected|repeating_spell-2_$14_spell) [PreparedTag](https://tinyurl.com/dndspell@{Selected|repeating_spell-2_$14_spellprepared}#.jpg) 
}}
```
