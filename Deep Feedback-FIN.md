[[_TOC_]]

# FEATURE HIERARCHY for FINNISH: for exercise feedback

Legend: Examples in parentheses: two forms that differ in this feature:
- [ correct! incorrect? ]
- [ possible-value-1 / possible-value-2 / possible-value-3 ]
- FEATURE names are upper-case


**Level/Depth dimension**: organize/group features for each POS into logical levels:

- Example of levels: (for verbs only):
- 1 Level: VERB_FORM feedback: mix of MOOD and other features
   - "kind of verb": infinitivie, indicative, participle, impersonal, ...
- 2 Level: feedback:  (error in suffix (Future: also prefix) — closer to core)
   - TENSE
   - (to add in future) REFLEXIVE/PASSIVE
   - ASPECT (perf/imperf :prefix)
- 3 Level: feedback: (error in ending — further from core)
   - NUMBER
   - CASE
   - GENDER (adjectives, participles, verbs)
- **LAST level: FOR ALL POSs** - (enclitic) particle -ko, -kin, -kaan, -han, -pa, -ka, -s
  - (later: handle TWO particles: +ko+han, +pa+s, ...)

**Retry dimension**: which retry and how vague/specific the feedback?
- Attempt-2 (Retry-1): vague feedback —— example: "Try another CASE"
   - this makes sense only for features with >2 values
      - for NUMBER (singular/plural) it's as good as retry 2
   - 🟊🟊🟊 DIRECT: for some features we give directly specific feedback (even if >2 values)
- **Attempt-3 (Retry-2) and all later attempts**: specific feedback —— example: "Use genitive CASE"
   - give specific instruction - on all Attempt-3+
- (This second dimension disappears for BINARY FEATURES with only two values in that place in the Hierarchy, in dimension 1)


**Ambiguity dimension:**
- **MUST KEEP IN MIND: we may not know which is the correct feature+value combination** 
  - in correct answer
  - in user's answer
because we have morphological ambiguity


# LEVELS of features for different POSs

- Column "+wrapper features"
  - contains ADDITIONAL wrapper features, needed to find the particular "LOGICAL" feature we are looking for
  - (logical: means NOT in analyzer, but what we believe / how would like to see the analysis )
  - this column is mostly empty, used in a few cases, where the analysis is convoluted — we need to check more than one feature.  since mostly we do follow the analyzer

## Noun

- Level 1:

  | feature   | feedback       | wrapper      | 1-token    |
  | --------- | -------------- | ------------ | ---------- |
  | NUMBER    | 🟊🟊🟊 (BINARY)   |              |            |
  |           | singular       | NUMBER=sg    | talo       |
  |           | plural         | NUMBER=pl    | talot      |
  | CASE      |                |              |            |
  |           | nominative     | CASE=nom     | talo       |
  |           | genitive       | CASE=gen     | talon      |
  |           | partitive      | CASE=par     | taloa      |
  |           | inessive       | CASE=ine     | talossa    |
  |           | adessive       | CASE=ade     | talolla    |
  |           | illative       | CASE=ill     | taloon     |
  |           | allative       | CASE=all     | talolle    |
  |           | elative        | CASE=ela     | talosta    |
  |           | ablative       | CASE=abl     | talolta    |
  |           | abessive       | CASE=abe     | talotta    |
  |           | translative    | CASE=tra     | taloksi    |
  |           | essive         | CASE=ess     | talona     |
  |           | commitative    | CASE=com     | taloineen  |

- Level 2:

  | feature    | feedback                  | wrapper        | 1-token  |
  | ---------- | ------------------------- | -------------- | -------- |
  | POSSES     | "Possessive suffix"       |                |          |
  |            | 1st-singular possessive   | POSSES=PxSg1   | taloni   |
  |            | 2nd-singular possessive   | POSSES=PxSg2   | talosi   |
  |            | 3rd person possessive     | POSSES=PxSg3   | talonsa  |
  |            | 1st-plural possessive     | POSSES=PxPl1   | talomme  |
  |            | 2nd-plural possessive     | POSSES=PxPl2   | talonne  |
  |            | 3rd person possessive     | POSSES=PxPl3   | talonsa  |


## Adjective

- Level 1:

  | feature | Feedback                  | wrapper           | 1-token  |
  | ------- | ------------------------- | ----------------- | -------- |
  | DEGREE  | 🟊🟊🟊 "Kind of adjective"   |                   |          |
  |         | positive                  | COMPAR=**none**   | isoa     |
  |         | comparative               | COMPAR=comp       | isompia  |
  |         | superlative               | COMPAR=sup        | isointa  |

- Level 2:
  
  | feature    | Feedback       | wrapper      | 1-token     |
  | ---------- | -------------- | ------------ | ----------- |
  | NUMBER     | 🟊🟊🟊 (BINARY)   |              |             |
  |            | singular       | NUMBER=sg    | iso         |
  |            | plural         | NUMBER=pl    | isot        |
  | CASE       |                |              |             |
  |            | nominative     | CASE=nom     | iso         |
  |            | genitive       | CASE=gen     | ison        |
  |            | partitive      | CASE=par     | isoa        |
  |            | inessive       | CASE=ine     | isossa      |
  |            | adessive       | CASE=ade     | isolla      |
  |            | illative       | CASE=ill     | isoon       |
  |            | allative       | CASE=all     | isolle      |
  |            | elative        | CASE=ela     | isosta      |
  |            | ablative       | CASE=abl     | isolta      |
  |            | abessive       | CASE=abe     | isotta      |
  |            | translative    | CASE=tra     | isoksi      |
  |            | essive         | CASE=ess     | isona       |
  |            | commitative    | CASE=com     | isoineen    |


## Verb

[All Verb inflections can be seen HERE in Wiktionary:](https://fi.wiktionary.org/wiki/Liite:Verbitaivutus/suomi/tehd%C3%A4)

- Level 1: artificial "magical feature" = "VERB_FORM" : 
  - if answer wrong on VERB_FORM, feedback only level 1: 
    - feedback (specific) = "you used X, please use Y"
    - (skip Retry 1 of Second dimension, go straight to specific feedback)

  | feature           | feedback            | wrapper                | chunker                         | 1-token   |
  | ----------------- | ------------------- | ---------------------- | ------------------------------- | --------- |
  | VERB_FORM         | 🟊🟊🟊 "Kind of verb"  |                        |                                 |           |
  | (non-finite)      | Infinitive          | INF_FORM=*             | --                              | sanoa     |
  | (finite)          | Indicative          | MOOD=Ind   + VOICE=Act | MOOD:Indicative + Voice:Active  | sanon     |
  | (finite)          | Conditional         | MOOD=Cond  + VOICE=Act | MOOD:Conditional + Voice:Active | sanoisin  |
  | (finite)          | Potential           | MOOD=Pot   + VOICE=Act | MOOD:Potential + Voice:Active   | sanonee   |
  | (finite)          | Imperative          | MOOD=Imprt + VOICE=Act | MOOD:Imperative + Voice:Active  | sano      |
  | (non-finite)      | Participle          | PARTICIPLE_FORM=*      | --                              | sanova    |
  | ???               | Impersonal          | PERSON=4 + VOICE=pss   | Voice:Passive                   | sanotaan  |
   
  - VERB_FORM = Infinitive
    - Level 2:
      
      | feature  | Feedback                    | wrapper                | 1-token        |
      | -------- | --------------------------- | ---------------------- | -------------- |
      | INF_TYPE | 🟊🟊🟊 "Kind of infinitive"    |                        |                |
      |          | A-Infinitive (I)            | INF_FORM=Inf-A         | sanoa          |
      |          | E-Infinitive (II)           | INF_FORM=Inf-E         | sanoen         |
      |          | Ma-Infinitive (III)         | INF_FORM=Inf-Ma        | sanomaan       |
      |          | (Der/)Minen-Infinitive (IV) | INF_FORM=Inf-Minen     | sanominen      |
      |          | (Der/)5th-Invinitive (V)    | INF_FORM=Inf-Maisilla  | sanomaisillaan |
      
      - INF_TYPE = Infinitive 1(A): **Wrapper: INF_FORM = Inf-A**
          - Level 3:

            | feature | feedback             | wrapper    | 1-token     |
            | ------- | -------------------- | ---------- | ----------- |
            | CASE    | 🟊🟊🟊 (BINARY)         |            |             |
            |         | Short (Lative)       | CASE=lat   | sanoa       |
            |         | Long (Translative)   | CASE=tra   | sanoakseen  |

      - INF_TYPE = Infinitive 2(E): **Wrapper: INF_FORM = Inf-E**
          - Level 3:

            | feature   | feedback        | wrapper           | 1-token     |            |
            | --------- | --------------- | ----------------- | ----------- | ---------- |
            | VOICE     | 🟊🟊🟊 (BINARY)    |                   |             |            |
            |           | active          | VOICE=act         | sanoessa    | tehdessä   |
            |           | passive         | VOICE=pss         | sanottaessa | tehtäessä  |
            | --------- | --------------- | ----------------- | ----------- | ---------- |
            | CASE      | 🟊🟊🟊 (BINARY)    |                   |             |            |
            |           | inessive        | CASE=ine          | sanoessa    | tehdessä   |
            |           | instructive     | CASE=ins          | sanoen      | tehden     |

          - CASE = Inessive:
            - Level 4:
  
              | feature  | feedback                   | wrapper       | 1-token                |
              | -------- | -------------------------- | ------------- | ------------           |
              | POSSES   | "Possessive suffix"        |               |                        |
              |          | 1st-singular possessive    | POSSES=PxSg1  | tehdessäni             |
              |          | 2nd-singular possessive    | POSSES=PxSg2  | tehdessäsi             |
              |          | 3rd person possessive      | POSSES=PxSg3  | tehdessään tehdessänsä |
              |          | 1st-plural possessive      | POSSES=PxPl1  | tehdessämme            |
              |          | 2nd-plural possessive      | POSSES=PxPl2  | tehdessänne            |
              |          | 3rd person possessive      | POSSES=PxPl3  | tehdessään tehdessänsä |

      - INF_TYPE = Infinitive 3(Ma): **Wrapper: INF_FORM = Inf-Ma**
          - Level 3:

            | feature   | feedback      | wrapper        | 1-token      |              |
            | --------- | ------------- | -------------- | ------------ | ------------ |
            | CASE      | (only 6)      |                |              |              |
            |           | inessive      | CASE=ine       | sanomassa    | tekemässä    |
            |           | elative       | CASE=ela       | sanomasta    | tekemästä    |
            |           | illative      | CASE=ill       | sanomaan     | tekemään     |
            |           | adessive      | CASE=ade       | sanomalla    | tekemällä    |
            |           | abessive      | CASE=abe       | sanomatta    | tekemättä    |
            |           | instructive   | CASE=ins       | sanoman      | tekemän      |

      - INF_TYPE = Infinitive 4(Der/Minen): **Wrapper: INF_FORM = Inf-Minen**
          - Level 3: (**Continue as NOUN inflection**)

            | feature    | feedback       | wrapper        | 1-token         |
            | ---------- | -------------- | -------------- | --------------- |
            | NUMBER     | 🟊🟊🟊 (BINARY)   |                |                 |
            |            | singular       | NUMBER=sg      | sanominen       |
            |            | plural         | NUMBER=pl      | sanomiset       |
            | CASE       |                |                |                 |
            |            | nominative     | CASE=nom       | sanominen       |
            |            | genitive       | CASE=gen       | sanomisen       |
            |            | partitive      | CASE=par       | sanomista       |
            |            | inessive       | CASE=ine       | sanomisessa     |
            |            | adessive       | CASE=ade       | sanomisella     |
            |            | illative       | CASE=ill       | sanomiseen      |
            |            | allative       | CASE=all       | sanomiselle     |
            |            | elative        | CASE=ela       | sanomisesta     |
            |            | ablative       | CASE=abl       | sanomiselta     |
            |            | abessive       | CASE=abe       | sanomisetta     |
            |            | translative    | CASE=tra       | sanomiseksi     |
            |            | essive         | CASE=ess       | sanomisena      |
            

          - Level 4:

            | feature  | feedback                   | wrapper       | 1-token      |
            | -------- | -------------------------- | ------------- | ------------ |
            | POSSES   | "Possessive suffix"        |               |              |
            |          | 1st-singular possessive    | POSSES=PxSg1  | sanomiseni   |
            |          | 2nd-singular possessive    | POSSES=PxSg2  | sanomisesi   |
            |          | 3rd person possessive      | POSSES=PxSg3  | sanomisensa  |
            |          | 1st-plural possessive      | POSSES=PxPl1  | sanomisemme  |
            |          | 2nd-plural possessive      | POSSES=PxPl2  | sanomisenne  |
            |          | 3rd person possessive      | POSSES=PxPl3  | sanomisensa  |

      - INF_TYPE = Infinitive 5(Der/Maisilla): **Wrapper: INF_FORM = Inf-Maisilla**
          - Level 3: (**Continue as NOUN inflection**)

            | feature | feedback                  | wrapper         | 1-token          |
            | ------- | ------------------------- | --------------- | ---------------- |
            | POSSES  | "Possessive suffix"       |                 |                  |
            |         | 1st-singular possessive   | POSSES=PxSg1    | sanomaisillani   |
            |         | 2nd-singular possessive   | POSSES=PxSg2    | sanomaisillasi   |
            |         | 3rd person possessive     | POSSES=PxSg3    | sanomaisillaan   |
            |         | 1st-plural possessive     | POSSES=PxPl1    | sanomaisillamme  |
            |         | 2nd-plural possessive     | POSSES=PxPl2    | sanomaisillanne  |
            |         | 3rd person possessive     | POSSES=PxPl3    | sanomaisillaan   |

      - **!!! BUG to fix: wrapper does not recognize this infinitive:** fix **Der/maisilla** to be value of INF_FORM (now = UNKNOWN)**

  - VERB_FORM = Indicative
    - Level 2:          (note (?) : past = imperfect)

      | feature  | feedback           | wrapper   | chunker              | 1-token       | multi-token       |                  |
      | -------  | ------------------ | --------- | -------------------- | ------------- | ----------------- | ---------------- |
      | TENSE    | "tense"            |           |                      |               |                   |                  |
      |          | present tense      | TENSE=prs | TENSE:Present        | sanoo tekee   | en sano           |                  |
      |          | imperfect tense    | TENSE=prt | TENSE:Imperfect      | sanoi teki    | en sanonut        |                  |
      |          | perfect tense      | —         | TENSE:Perfect        | —             | olen sanonut      | olen tehnyt      |
      |          | pluperfect tense   | —         | TENSE:Pluperfect     | —             | olin sanonut      | olin tehnyt      |
      | -------  | ------------------ | --------- | -------------------- | ------------- | ----------------- | ---------------- |
      | POLARITY | 🟊🟊🟊 (BINARY)       |           |                      |               |                   |                  |
      |          | positive           | —         | POLARITY:Positive    | —             | olen sanonut      | olen tehnyt      |
      |          | negative           | —         | POLARITY:Negative    | —             | en ole sanonut    | en ole tehnyt    |

    - Level 3:

      | feature | feedback       | wrapper       | 1-token   |          |
      | ------- | -------------- | ------------- | --------- | -------- |
      | NUMBER  | 🟊🟊🟊 (BINARY)   |               |           |          |
      |         | singular       | NUMBER=sg     | sanoo     | tekee    |
      |         | plural         | NUMBER=pl     | sanovat   | tekevät  |
      | ------- | -------------- | ------------- | --------- | -------- |
      | PERSON  |                |               |           |          |
      |         | 1st person     | PERSON=1      | sanon     | teen     |
      |         | 2nd person     | PERSON=2      | sanot     | teet     |
      |         | 3rd person     | PERSON=3      | sanoo     | tekee    |

  - VERB_FORM = Conditional mood
    - Level 2:

      | feature  | feedback           | wrapper       | chunker            | 1-token          | multi-token       |
      | -------  | ------------------ | ------------- | ------------------ | ---------------- | ----------------- |
      | TENSE    | 🟊🟊🟊 (BINARY)       |               |                    |                  |                   |
      |          | present tense      | TENSE=prs     | TENSE:Present      | sanoisin         | en sanoisi        |
      |          | perfect tense      | —             | TENSE:Perfect      | —                | olisin sanonut    |
      | -------  | ------------------ | ------------- | ------------------ | ---------------- | ----------------- |
      | POLARITY | 🟊🟊🟊 (BINARY)       |               | 🟊🟊🟊 (BINARY)       |                  |                   |
      |          | positive           | —             | POLARITY:Positive  | sanoisin         | olisin sanonut    |
      |          | negative           | —             | POLARITY:Negative  | —                | en olisi sanonut  |


    - Level 3:

      | feature   | feedback        | wrapper      | 1-token       |             |
      | --------- | --------------- | ------------ | ------------- | ----------- |
      | NUMBER    | 🟊🟊🟊 (BINARY)    |              |               |             |
      |           | singular        | NUMBER=sg    | sanoisi       | tekisi      |
      |           | plural          | NUMBER=pl    | sanoisivat    | tekisivät   |
      | --------- | --------------- | ------------ | ------------- | ----------- |
      | PERSON    |                 |              |               |             |
      |           | 1st person      | PERSON=1     | sanoisin      | tekisin     |
      |           | 2nd person      | PERSON=2     | sanoisit      | tekisit     |
      |           | 3rd person      | PERSON=3     | sanoisi       | tekisi      |

  - VERB_FORM =  Potential mood
    - Level 2:

      | feature   | feedback           | wrapper    | chunker            | 1-token          | multi-token       |                  |
      | --------- | ------------------ | ---------- | ------------------ | ---------------- | ----------------- | ---------------- |
      | TENSE     | 🟊🟊🟊 (BINARY)       |            |                    |                  |                   |                  |
      |           | present tense      | TENSE=prs  | TENSE:Present      | sanoen  tehnen   |                   |                  |
      |           | perfect tense      | —          | TENSE:Perfect      | —                | lienen sanonut    | lienen tehnyt    |
      | --------- | ------------------ | ---------- | ------------------ | ---------------- | ----------------- | ---------------- |
      | POLARITY  | 🟊🟊🟊 (BINARY)       |            |                    |                  |                   |                  |
      |           | positive           | —          | POLARITY:Positive  | —                | en sanone         | en tehne         |
      |           | negative           | —          | POLARITY:Negative  | —                | en liene sanonut  | en liene tehnyt  |

    - Level 3:

      | feature | feedback        | wrapper    | 1-token     |             |
      | ------- | --------------- | ---------- | ----------- | ----------- |
      | NUMBER  | 🟊🟊🟊 (BINARY)    |            |             |             |
      |         | singular        | NUMBER=sg  | sanonen     | tehnen      |
      |         | plural          | NUMBER=pl  | sanonemme   | tehnemme    |
      | ------- | --------------- | ---------- | ----------- | ----------- |
      | PERSON  |                 |            |             |             |
      |         | 1st person      | PERSON=1   | sanonen     | tehnen      |
      |         | 2nd person      | PERSON=2   | sanonet     | tehnet      |
      |         | 3rd person      | PERSON=3   | sanonee     | tehnee      |

  - VERB_FORM =  Imperative mood
    - Level 2:

      | feature   | feedback           | wrapper   | chunker            | 1-token     | multi-token         |
      | --------- | ------------------ | --------- | ------------------ | ----------- | ------------------- |
      | TENSE     | 🟊🟊🟊 (BINARY)       |           |                    |             |                     |
      |           | present tense      | TENSE=prs | TENSE:Present      | sanokoon    |                     |
      |           | perfect tense      | —         | TENSE:Perfect      | —           | olkoon sanonut      |
      | --------- | ------------------ | --------- | ------------------ | ----------- | ------------------- |
      | POLARITY  | 🟊🟊🟊 (BINARY)       |           |                    |             |                     |
      |           | positive           | —         | POLARITY:Positive  | —           | älköön sanoko       |
      |           | negative           | —         | POLARITY:Negative  | —           | älköön olko sanonut |

    - Level 3:

      | feature | feedback      | wrapper     | 1-token       |
      | ------- | ------------- | ----------- | ------------- |
      | NUMBER  | 🟊🟊🟊 (BINARY)  |             |               |
      |         | singular      | NUMBER=sg   | sano          |
      |         | plural        | NUMBER=pl   | sanokaa       |
      | ------- | ------------- | ----------- | ------------- |
      | PERSON  |               |             |               |
      |         | 1st person    | PERSON=1    | sanokaamme    |
      |         | 2nd person    | PERSON=2    | sanokaa       |
      |         | 3rd person    | PERSON=3    | sanokoot      |

  - VERB_FORM =  Participle
    - **Easy exercise**: PARTICIPLE base was given, so we know it's a participle, behaves like ADJECTIVE, except for DEGREE/COMPAR feature
      - Level 2:

        | feature | feedback     | wrapper     | 1-token         |
        | ------- | ------------ | ----------- | --------------- |
        | NUMBER  | 🟊🟊🟊 (BINARY) |             |                 |
        |         | singular     | NUMBER=sg   | sanottava       |
        |         | plural       | NUMBER=pl   | sanottavat      |
        | CASE    |              |             |                 |
        |         | nominative   | CASE=nom    | sanottava       |
        |         | genitive     | CASE=gen    | sanottavan      |
        |         | partitive    | CASE=par    | sanottavaa      |
        |         | inessive     | CASE=ine    | sanottavassa    |
        |         | adessive     | CASE=ade    | sanottavalla    |
        |         | illative     | CASE=ill    | sanottavaon     |
        |         | allative     | CASE=all    | sanottavalle    |
        |         | elative      | CASE=ela    | sanottavasta    |
        |         | ablative     | CASE=abl    | sanottavalta    |
        |         | abessive     | CASE=abe    | sanottavatta    |
        |         | translative  | CASE=tra    | sanottavaksi          |
        |         | essive       | CASE=ess    | sanottavana           |

    - **Hard exercise**: VERB base was given, behaves **first** like a verb, then like ADJECTIVE, except for DEGREE/COMPAR feature
      - **TODO: include AGENTIVE participle** (may need to refactor VOICE x TENSE into 4 explicit forms + AGENTIVE )
      - Level 2:

        | feature | feedback        | wrapper                  | 1-token     |
        | ------- | --------------- | ------------------------ | ----------- |
        | VOICE   | 🟊🟊🟊 (BINARY)    |                          |             |
        |         | Active          | VOICE=Act                | sanova      |
        |         | Passive         | VOICE=Pss                | sanottava   |
        | ------- | --------------- | ------------------------ | ----------- |
        | TENSE   | 🟊🟊🟊 (BINARY)    |                          |             |
        |         | Present         | PARTICIPLE_FORM=PrsPrc   | sanova      |
        |         | Past            | PARTICIPLE_FORM=PrfPrc   | sanonut     |

      - Level 3: **NOTE: this Level is identical to Easy Participle Level 1**

        | feature | feedback        | wrapper       | 1-token         |
        | ------- | --------------- | ------------- | --------------- |
        | NUMBER  | 🟊🟊🟊 (BINARY)    |               |                 |
        |         | singular        | NUMBER=sg     | sanottava       |
        |         | plural          | NUMBER=pl     | sanottavat      |
        | CASE    |                 |               |                 |
        |         | nominative      | CASE=nom      | sanottava       |
        |         | genitive        | CASE=gen      | sanottavan      |
        |         | partitivep      | CASE=par      | sanottavaa      |
        |         | inessive        | CASE=ine      | sanottavassa    |
        |         | adessive        | CASE=ade      | sanottavalla    |
        |         | illative        | CASE=ill      | sanottavaon     |
        |         | allative        | CASE=all      | sanottavalle    |
        |         | elative         | CASE=ela      | sanottavasta    |
        |         | ablative        | CASE=abl      | sanottavalta    |
        |         | abessive        | CASE=abe      | sanottavatta    |
        |         | translative     | CASE=tra      | sanottavaksi    |
        |         | essive          | CASE=ess      | sanottavana     |

      - Level 4:

        | feature | feedback                  | wrapper         | 1-token        |
        | ------- | ------------------------- | --------------- | -------------- |
        | POSSES  | "possessive suffix"       |                 |                |
        |         | 1st-singular possessive   | POSSES=PxSg1    | sanomissani    |
        |         | 2nd-singular possessive   | POSSES=PxSg2    | sanomissasi    |
        |         | 1st-plural possessive     | POSSES=PxPl1    | sanomissamme   |
        |         | 2nd-plural possessive     | POSSES=PxPl2    | sanomissanne   |
        |         | 3rd person possessive     | POSSES=PxSg3    | sanomissaan    |
        |         | 3rd person possessive     | POSSES=PxPl3    | sanomissaan    |

  - VERB_FORM = **Passive-impersonal** wrapper: VOICE=pss + Person = 4
    - Level 2:
      - **(FIXED) Wrapper bug: Pe4 unknown ⇒ `Person = Impersonal`** 

      | feature | feedback         | wrapper       | chunker             | 1-token         | multi-token         | notes                  |
      | ------- | ---------------- | ------------- | ------------------- | --------------- | ------------------- | ---------------------- |
      | MOOD    | 🟊🟊🟊              |               |                     |                 |                     |                        |
      |         | indicative       | MOOD=Ind      | MOOD:Indicative     | sanotaan        | en sano             | all 4 tenses           |
      |         | conditional      | MOOD=Cond     | MOOD:Conditional    | sanottaisiin    | olisi sanottu       | only Present + Perfect |
      |         | potential        | MOOD=Pot      | MOOD:Potential      | sanottaneen     | lienee sanottu      | only Present + Perfect |
      |         | imperative       | MOOD=Imprt    | MOOD:Imperative     | sanottakoon     | olkoon sanottu      | only Present + Perfect |

    - Level 3:
      - Note: TENSE is 🟊🟊🟊 (BINARY) for all Moods except indicative, non-binary for Indicative

      | feature  | feedback           | wrapper       | chunker             | 1-token         | multi-token         | notes            |
      | -------- | ------------------ | ------------- | ------------------- | --------------- | ------------------- | ---------------- |
      | TENSE    | "tense"            |               |                     |                 |                     |                  |
      |          | present tense      | TENSE=prs     | TENSE:Present       | sanotaan        | en sano             | all moods        |
      |          | imperfect tense    | TENSE=prt     | TENSE:Imperfect     | sanottiin       | en sanonut          | only Indicative  |
      |          | perfect tense      | —             | TENSE:Perfect       | —               | olen sanonut        | all moods        |
      |          | pluperfect tense   | —             | TENSE:Pluperfect    | —               | olin sanonut        | only Indicative  |
      | -------- | ------------------ | ------------- | ------------------- | --------------- | ------------------- | ---------------- |
      | POLARITY | 🟊🟊🟊 (BINARY)       |               |                     |                 |                     |                  |
      |          | positive           | —             | POLARITY:Positive   | —               | olkoon sanottu      |                  |
      |          | negative           | —             | POLARITY:Negative   | —               | älköön olko sanottu |                  |
      

## PRONOUN

- features for **PRON_CLASS** one of:

  | wrapper/analyzer  | Pronoun type   | Examples                      |
  | ----------------- | -------------- | ----------------------------- |
  | dem               | Demonstrative  | tämän, tällä, tuon, tuolla    |
  | indef             | Indefinite     | joka, joksikuksi              |
  | interr            | Interrogative  | kuka, kenet, kenettä          |
  | pers              | Personal       | minä, minun, minut            |
  | qu                | Quantitative   | monta, moneen                 |
  | recipr            | Reciprocal     | toisiaan,                     |
  | refl              | Reflexive      | itse, itselleen, itsekseen    |
  | rel               | Relative       | joka, kenet                   |

  - Notes:
    - When LEMMA has multiple readings with different PRON_CLASS: **this not an ambiguity**:
      - all other tags will be identical
      - e.g.: Relative class is **always also either Indefinite or Interrogative**
    - *possessive suffix*: only with Recipr and Refl
      - *Reciprocal* must have possessive suffix
    - *Accusative* case exists only for pronouns

- Level 1:

  | feature   | feedback       | wrapper      | 1-token    |
  | --------- | -------------- | ------------ | ---------- |
  | NUMBER    | 🟊🟊🟊 (BINARY)   |              |            |
  |           | singular       | NUMBER=sg    | kuka       |
  |           | plural         | NUMBER=pl    | ketkä      |
  | --------- | -------------- | ------------ | ---------- |
  | CASE      |                |              |            |
  |           | nominative     | CASE=nom     | kuka       |
  |           | genitive       | CASE=gen     | kenen      |
  | ***       | accusative     | CASE=acc     | kenet      |
  |           | partitive      | CASE=par     | ketä       |
  |           | inessive       | CASE=ine     | kenessä    |
  |           | adessive       | CASE=ade     | kenellä    |
  |           | illative       | CASE=ill     | keneen     |
  |           | allative       | CASE=all     | kenelle    |
  |           | elative        | CASE=ela     | kenestä    |
  |           | ablative       | CASE=abl     | keneltä    |
  |           | abessive       | CASE=abe     | kenettä    |
  |           | translative    | CASE=tra     | keneksi    |
  |           | essive         | CASE=ess     | kenenä     |

- Level 2:

  | feature | feedback                  | wrapper         | 1-token        |
  | ------- | ------------------------- | --------------- | -------------- |
  | POSSES  | "possessive suffix"       |                 |                |
  |         | 1st-singular possessive   | POSSES=PxSg1    | itselleni      |
  |         | 2nd-singular possessive   | POSSES=PxSg2    | itsellesi      |
  |         | 1st-plural possessive     | POSSES=PxPl1    | itsellemme     |
  |         | 2nd-plural possessive     | POSSES=PxPl2    | itsellenne     |
  |         | 3rd person possessive     | POSSES=PxSg3    | itselleen      |
  |         | 3rd person possessive     | POSSES=PxPl3    | itselleen      |

...

## NUMERAL
...

## TODO

- ??? maybe move passive impersonal indicative and conditional under indicative mood
   - as it is in Wiktionary tables
+ fix wrapper bug: **Pe4**
- *periphrastic verbs*: 
   - make chunks `[ modal + main-verb ]`, `[ negation + main-verb ]`,
      - then create more feedback for forms involving periprhasis
   - **verb NEGATION**: `en tee`, `en tehnyt`, ...
   - **perfect tense**: `olen tehnyt`, ... -- **now all perfect forms are missing**

## NOTES:

- Problem 1: (WORKS!)
   - correct surface: surface ambiguity: "pitää":
      - (to hold)  0. infinitiveA (Inf-A)
      - (he holds) 0. indicative 1. TENSE = present 2. PERSON = 3, NUMBER = singular 
   - user answer: piti = 0. VERB-TOP-FEATURE = indicative 1. TENSE = past 2. PERSON = 3, NUMBER = singular

- Problem 2: (WORKS!)
   - correct surface: piti = 0. VERB-TOP-FEATURE = indicative 1. TENSE=past 2. PERSON = 3, NUMBER = singular
   - user answer: surface ambiguity: "pitää": 
      - (to hold)  0. VERB-TOP-FEATURE = infinitiveA (Inf-A)
      - (he holds) 0. VERB-TOP-FEATURE = indicative 1. TENSE = present 2. PERSON = 3, NUMBER = singular 

- Problem 3: feature is missing from user answer
   - correct surface: halusit = 0. VERB-TOP-FEATURE = indicative 1. TENSE=past 2. PERSON = 2, NUMBER = singular
   - user answer: surface ambiguity: "haluta":
      - (to want)  0. VERB-TOP-FEATURE = infinitiveA (Inf-A)


____________________________________________________________________________

| **Impersonal-passive+indicative**  | VOICE=pss + MOOD=indicative                      |
| **Impersonal-passive+conditional** | VOICE=pss + MOOD=conditional                     |
