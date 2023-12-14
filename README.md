# Preliminary Explorations into Tokenization for Neo-Aramaic

This is the final product submission for LING 98A at Harvard University.

## Note to Hayley

Hi Hayley. This is being submitted late because home is an unideal place to work from. I also do not get to do clever experimenting where I qualitatively compare tokenization methods and different splits of the dataset. However, I am extremely excited to explore this more and think critically on ways forward over the winter break.

## Introduction

This project represents an initial foray into the complex world of text tokenization for Neo-Aramaic, a language with unique morphological challenges. Neo-Aramaic, as a Semitic language, presents a fascinating case study due to its non-Indo-European roots and intricate morphological structures. 

The aim of this project is to evaluate the effectiveness of different tokenization strategies in handling the linguistic nuances of Neo-Aramaic. This exploration is crucial for developing more advanced Natural Language Processing (NLP) applications for underrepresented languages like Neo-Aramaic.

## Repository Structure

```
nena-tokenizer/
├── datasets/
│   ├── khan2016/
│   │   ├── all.txt
│   │   ├── A1.pb.txt
│   │   └── ...
│   └── nazari2023/
│       ├── all.txt
│       ├── id123456789
│       └── ...
├── research/
│   ├── literature/
│   │   └── ahmadi2020toward.pdf
│   │   └── ...
│   └── notes.md
├── vocab/
│   ├── khan2016_vocab_bpe.txt
│   └── ...
├── samples/
│   ├── khan2016_šəmma_tokens_bpe.txt
│   └── ...
├── README.md
├── requirements.txt
└── main.ipynb
```

## Methodology

This project utilizes three tokenization methods: Byte-Pair Encoding (BPE), Unigram, and WordPiece. These methods were chosen for their prevalence in NLP and their varied approaches to text segmentation. The tokenization processes were applied to two distinct datasets: 'khan2016', a grammatical description corpus, and 'nazari2023', a comprehensive inflectional database. The goal was to observe how each tokenizer handles the morphological complexity of Neo-Aramaic.

### Data and Tools

- **Datasets:** The 'khan2016' and 'nazari2023' datasets provide a rich linguistic resource, encompassing a wide array of morphological variations in Neo-Aramaic.
- **Tokenizers:** The BPE, Unigram, and WordPiece tokenizers represent different strategies for segmenting text, each with its strengths and weaknesses in handling complex morphology.

### Experiment

The experiment involved applying each tokenizer to a selected set of words from the datasets, analyzing the token outputs, and comparing them against ideal tokenization targets. This process aimed to gauge the efficacy of each method in accurately capturing the morphological subtleties of Neo-Aramaic.

## Results and Observations

| Word        | Dataset    | Tokenizer | Tokens                          |
|-------------|------------|-----------|---------------------------------|
| bnátə       | khan2016   | bpe       | b, n, [UNK], tə                 |
| bnátə       | khan2016   | unigram   | b, n, á, t, ə                   |
| bnátə       | khan2016   | wordpiece | [UNK]                           |
| bnátə       | nazari2023 | bpe       | bn, [UNK], tə                   |
| bnátə       | nazari2023 | unigram   | b, n, á, t, ə                   |
| bnátə       | nazari2023 | wordpiece | [UNK]                           |
| bráta       | khan2016   | bpe       | br, [UNK], ta                   |
| bráta       | khan2016   | unigram   | b, r, á, ta                     |
| bráta       | khan2016   | wordpiece | [UNK]                           |
| bráta       | nazari2023 | bpe       | br, [UNK], ta                   |
| bráta       | nazari2023 | unigram   | b, r, á, t, a                   |
| bráta       | nazari2023 | wordpiece | [UNK]                           |
| dára        | khan2016   | bpe       | d, [UNK], ra                    |
| dára        | khan2016   | unigram   | d, á, ra                        |
| dára        | khan2016   | wordpiece | [UNK]                           |
| dára        | nazari2023 | bpe       | d, [UNK], ra                    |
| dára        | nazari2023 | unigram   | d, á, ra                        |
| dára        | nazari2023 | wordpiece | [UNK]                           |
| maváy       | khan2016   | bpe       | mav, [UNK], y                   |
| maváy       | khan2016   | unigram   | mav, á, y                       |
| maváy       | khan2016   | wordpiece | [UNK]                           |
| maváy       | nazari2023 | bpe       | mav, [UNK], y                   |
| maváy       | nazari2023 | unigram   | ma, v, á, y                     |
| maváy       | nazari2023 | wordpiece | [UNK]                           |
| máta        | khan2016   | bpe       | m, [UNK], ta                    |
| máta        | khan2016   | unigram   | m, á, ta                        |
| máta        | khan2016   | wordpiece | [UNK]                           |
| máta        | nazari2023 | bpe       | m, [UNK], ta                    |
| máta        | nazari2023 | unigram   | m, á, t, a                      |
| máta        | nazari2023 | wordpiece | [UNK]                           |
| pála        | khan2016   | bpe       | p, [UNK], la                    |
| pála        | khan2016   | unigram   | p, á, la                        |
| pála        | khan2016   | wordpiece | [UNK]                           |
| pála        | nazari2023 | bpe       | p, [UNK], la                    |
| pála        | nazari2023 | unigram   | p, á, la                        |
| pála        | nazari2023 | wordpiece | [UNK]                           |
| savə́lta    | khan2016   | bpe       | savə́lta                        |
| savə́lta    | khan2016   | unigram   | savə́lt, a                      |
| savə́lta    | khan2016   | wordpiece | savə́lta                        |
| savə́lta    | nazari2023 | bpe       | savə́l, ta                      |
| savə́lta    | nazari2023 | unigram   | savə́lt, a                      |
| savə́lta    | nazari2023 | wordpiece | sav, ##ə́lta                    |
| sólə        | khan2016   | bpe       | s, [UNK], lə                    |
| sólə        | khan2016   | unigram   | s, ó, lə                        |
| sólə        | khan2016   | wordpiece | [UNK]                           |
| sólə        | nazari2023 | bpe       | s, [UNK], lə                    |
| sólə        | nazari2023 | unigram   | s, ó, lə                        |
| sólə        | nazari2023 | wordpiece | [UNK]                           |
| tála        | khan2016   | bpe       | t, [UNK], la                    |
| tála        | khan2016   | unigram   | t, á, la                        |
| tála        | khan2016   | wordpiece | [UNK]                           |
| tála        | nazari2023 | bpe       | t, [UNK], la                    |
| tála        | nazari2023 | unigram   | t, á, la                        |
| tála        | nazari2023 | wordpiece | [UNK]                           |
| váda       | khan2016   | bpe       | váda                           |
| váda       | khan2016   | unigram   | váda                           |
| váda       | khan2016   | wordpiece | váda                           |
| váda       | nazari2023 | bpe       | vá, da                         |
| váda       | nazari2023 | unigram   | vád, a                         |
| váda       | nazari2023 | wordpiece | vád, ##a                       |
| vúdun      | khan2016   | bpe       | vúd, un                        |
| vúdun      | khan2016   | unigram   | vúd, un                        |
| vúdun      | khan2016   | wordpiece | vúd, ##un                      |
| vəttéla    | khan2016   | bpe       | vəttéla                        |
| vəttéla    | khan2016   | unigram   | vətté, la                      |
| vəttéla    | khan2016   | wordpiece | vəttéla                        |
| və́dli      | khan2016   | bpe       | və́dli                          |
| və́dli      | khan2016   | unigram   | və́dl, i                        |
| və́dli      | khan2016   | wordpiece | və́dli                          |
| yémišu      | khan2016   | bpe       | y, [UNK], mi, šu                |
| yémišu      | khan2016   | unigram   | y, é, mi, šu                    |
| yémišu      | khan2016   | wordpiece | [UNK]                           |
| yémišu      | nazari2023 | bpe       | y, [UNK], mi, šu                |
| yémišu      | nazari2023 | unigram   | y, é, m, i, šu                  |
| yémišu      | nazari2023 | wordpiece | [UNK]                           |
| yéməš       | khan2016   | bpe       | y, [UNK], məš                   |
| yéməš       | khan2016   | unigram   | y, é, məš                       |
| yéməš       | khan2016   | wordpiece | [UNK]                           |
| yéməš       | nazari2023 | bpe       | y, [UNK], məš                   |
| yéməš       | nazari2023 | unigram   | y, é, məš                       |
| yéməš       | nazari2023 | wordpiece | [UNK]                           |
| šə́mma      | khan2016   | bpe       | šə́mma                          |
| šə́mma      | khan2016   | unigram   | šə́mm, a                        |
| šə́mma      | khan2016   | wordpiece | šə́, ##mma                      |
| šə́mma      | nazari2023 | bpe       | šə́m, ma                        |
| šə́mma      | nazari2023 | unigram   | šə́mm, a                        |
| šə́mma      | nazari2023 | wordpiece | šə́mm, ##a                      |
| šə́mmu      | khan2016   | bpe       | šə́mmu                          |
| šə́mmu      | khan2016   | unigram   | šə́mmu                          |
| šə́mmu      | khan2016   | wordpiece | šə́mmu                          |
| šə́mmu      | nazari2023 | bpe       | šə́m, mu                        |
| šə́mmu      | nazari2023 | unigram   | šə́mm, u                        |
| šə́mmu      | nazari2023 | wordpiece | šə́mm, ##u                      |
| šə́mmuna    | khan2016   | bpe       | šə́mmu, na                      |
| šə́mmuna    | khan2016   | unigram   | šə́mmu, na                      |
| šə́mmuna    | khan2016   | wordpiece | šə́mmu, ##na                    |
| šə́mmuna    | nazari2023 | bpe       | šə́, mmuna                      |
| šə́mmuna    | nazari2023 | unigram   | šə́mm, u, na                    |
| šə́mmuna    | nazari2023 | wordpiece | šə́mm, ##una                    |
| ʾávəd      | khan2016   | bpe       | ʾávəd                          |
| ʾávəd      | khan2016   | unigram   | ʾávə, d                        |
| ʾávəd      | khan2016   | wordpiece | ʾávəd                          |
| ʾávəd      | nazari2023 | bpe       | ʾá, vəd                        |
| ʾávəd      | nazari2023 | unigram   | ʾáv, ə, d                      |
| ʾávəd      | nazari2023 | wordpiece | ʾáv, ##əd                      |
| ʾoda        | khan2016   | bpe       | ʾo, da                          |
| ʾoda        | khan2016   | unigram   | ʾoda                            |
| ʾoda        | khan2016   | wordpiece | ʾod, ##a                        |
| ʾoda        | nazari2023 | bpe       | ʾo, da                          |
| ʾoda        | nazari2023 | unigram   | ʾ, o, da                        |
| ʾoda        | nazari2023 | wordpiece | ʾod, ##a                        |
| ʾodána     | khan2016   | bpe       | ʾodána                         |
| ʾodána     | khan2016   | unigram   | ʾo, dána                       |
| ʾodána     | khan2016   | wordpiece | ʾodána                         |
| ṱanṱannána | khan2016   | bpe       | ṱa, n, ṱa, n, ná, na           |
| ṱanṱannána | khan2016   | unigram   | ṱ, an, ṱ, an, na, ́na           |
| ṱanṱannána | khan2016   | wordpiece | ṱa, ##n, ##ṱa, ##n, ##nána     |
| ṱanṱannána | nazari2023 | bpe       | [UNK], an, [UNK], an, n, ána   |
| ṱanṱannána | nazari2023 | unigram   | ṱ, an, ṱ, an, n, á, na         |
| ṱanṱannána | nazari2023 | wordpiece | [UNK]                           |
| ṱanṱanta    | khan2016   | bpe       | ṱa, n, ṱa, nta                  |
| ṱanṱanta    | khan2016   | unigram   | ṱ, an, ṱ, an, ta                |
| ṱanṱanta    | khan2016   | wordpiece | ṱa, ##n, ##ṱa, ##nta            |
| ṱanṱanta    | nazari2023 | bpe       | [UNK], an, [UNK], an, ta        |
| ṱanṱanta    | nazari2023 | unigram   | ṱ, an, ṱ, an, t, a              |
| ṱanṱanta    | nazari2023 | wordpiece | [UNK]                           |
| ṱanṱúnələ  | khan2016   | bpe       | ṱa, n, ṱú, nələ                |
| ṱanṱúnələ  | khan2016   | unigram   | ṱ, an, ṱú, nələ                |
| ṱanṱúnələ  | khan2016   | wordpiece | ṱa, ##n, ##ṱú, ##nələ          |
| ṱanṱúnələ  | nazari2023 | bpe       | [UNK], an, [UNK], únələ        |
| ṱanṱúnələ  | nazari2023 | unigram   | ṱ, an, ṱ, u, ́n, ə, lə          |
| ṱanṱúnələ  | nazari2023 | wordpiece | [UNK]                           |
| ṱanṱənnála | khan2016   | bpe       | ṱa, n, ṱən, ná, la             |
| ṱanṱənnála | khan2016   | unigram   | ṱ, an, ṱən, n, ála             |
| ṱanṱənnála | khan2016   | wordpiece | ṱa, ##n, ##ṱən, ##ná, ##la     |
| ṱanṱənnála | nazari2023 | bpe       | [UNK], an, [UNK], ənn, ála     |
| ṱanṱənnála | nazari2023 | unigram   | ṱ, an, ṱ, ən, n, á, la         |
| ṱanṱənnála | nazari2023 | wordpiece | [UNK]                           |
| ṱanṱə́nla   | khan2016   | bpe       | ṱa, n, ṱ, ə́n, la               |
| ṱanṱə́nla   | khan2016   | unigram   | ṱ, an, ṱ, ə́n, la               |
| ṱanṱə́nla   | khan2016   | wordpiece | ṱa, ##n, ##ṱə, ##́, ##n, ##la   |
| ṱanṱə́nla   | nazari2023 | bpe       | [UNK], an, [UNK], ə́nla         |
| ṱanṱə́nla   | nazari2023 | unigram   | ṱ, an, ṱ, ə, ́n, la             |
| ṱanṱə́nla   | nazari2023 | wordpiece | [UNK]                           |
| ṱanṱə́nna   | khan2016   | bpe       | ṱa, n, ṱə́nna                   |
| ṱanṱə́nna   | khan2016   | unigram   | ṱ, an, ṱ, ə́nna                 |
| ṱanṱə́nna   | khan2016   | wordpiece | ṱa, ##n, ##ṱə, ##́, ##n, ##na   |
| ṱanṱə́nna   | nazari2023 | bpe       | [UNK], an, [UNK], ə́nna         |
| ṱanṱə́nna   | nazari2023 | unigram   | ṱ, an, ṱ, ə, ́n, na             |
| ṱanṱə́nna   | nazari2023 | wordpiece | [UNK]                           |
| ṱánṱən     | khan2016   | bpe       | ṱá, n, ṱən                     |
| ṱánṱən     | khan2016   | unigram   | ṱ, án, ṱən                     |
| ṱánṱən     | khan2016   | wordpiece | ṱá, ##n, ##ṱən                 |
| ṱánṱən     | nazari2023 | bpe       | [UNK], án, [UNK], ən           |
| ṱánṱən     | nazari2023 | unigram   | ṱ, á, n, ṱ, ən                 |
| ṱánṱən     | nazari2023 | wordpiece | [UNK]                           |
| ṱunṱə́nla   | khan2016   | bpe       | ṱun, ṱ, ə́n, la                 |
| ṱunṱə́nla   | khan2016   | unigram   | ṱ, un, ṱ, ə́n, la               |
| ṱunṱə́nla   | khan2016   | wordpiece | ṱun, ##ṱə, ##́, ##n, ##la       |
| ṱunṱə́nla   | nazari2023 | bpe       | [UNK], un, [UNK], ə́nla         |
| ṱunṱə́nla   | nazari2023 | unigram   | ṱ, un, ṱ, ə, ́n, la             |
| ṱunṱə́nla   | nazari2023 | wordpiece | [UNK]                           |
| ṱunṱə́nna   | khan2016   | bpe       | ṱun, ṱə́nna                     |
| ṱunṱə́nna   | khan2016   | unigram   | ṱ, un, ṱ, ə́nna                 |
| ṱunṱə́nna   | khan2016   | wordpiece | ṱun, ##ṱə, ##́, ##n, ##na       |
| ṱunṱə́nna   | nazari2023 | bpe       | [UNK], un, [UNK], ə́nna         |
| ṱunṱə́nna   | nazari2023 | unigram   | ṱ, un, ṱ, ə, ́n, na             |
| ṱunṱə́nna   | nazari2023 | wordpiece | [UNK]                           |
| ṱunṱə́nnana | khan2016   | bpe       | ṱun, ṱə́nna, na                 |
| ṱunṱə́nnana | khan2016   | unigram   | ṱ, un, ṱ, ə́nna, na             |
| ṱunṱə́nnana | khan2016   | wordpiece | ṱun, ##ṱə, ##́, ##nnan, ##a     |
| ṱunṱə́nnana | nazari2023 | bpe       | [UNK], un, [UNK], ə́nnan, a     |
| ṱunṱə́nnana | nazari2023 | unigram   | ṱ, un, ṱ, ə, ́n, na, na         |
| ṱunṱə́nnana | nazari2023 | wordpiece | [UNK]                           |
| ṱunṱə́nnola | khan2016   | bpe       | ṱun, ṱ, ə́n, no, la             |
| ṱunṱə́nnola | khan2016   | unigram   | ṱ, un, ṱə́nn, ola               |
| ṱunṱə́nnola | khan2016   | wordpiece | ṱun, ##ṱə, ##́, ##n, ##no, ##la |
| ṱunṱə́nnola | nazari2023 | bpe       | [UNK], un, [UNK], ə́nnola       |
| ṱunṱə́nnola | nazari2023 | unigram   | ṱ, un, ṱ, ə, ́n, n, o, la       |
| ṱunṱə́nnola | nazari2023 | wordpiece | [UNK]                           |
| ⁺dára       | khan2016   | bpe       | ⁺, d, [UNK], ra                 |
| ⁺dára       | khan2016   | unigram   | ⁺, d, á, ra                     |
| ⁺dára       | khan2016   | wordpiece | ⁺, [UNK]                        |
| ⁺dára       | nazari2023 | bpe       | ⁺, d, [UNK], ra                 |
| ⁺dára       | nazari2023 | unigram   | ⁺, d, á, ra                     |
| ⁺dára       | nazari2023 | wordpiece | ⁺, [UNK]                        |
| ⁺pála       | khan2016   | bpe       | ⁺, p, [UNK], la                 |
| ⁺pála       | khan2016   | unigram   | ⁺, p, á, la                     |
| ⁺pála       | khan2016   | wordpiece | ⁺, [UNK]                        |
| ⁺pála       | nazari2023 | bpe       | ⁺, p, [UNK], la                 |
| ⁺pála       | nazari2023 | unigram   | ⁺, p, á, la                     |
| ⁺pála       | nazari2023 | wordpiece | ⁺, [UNK]                        |
| ⁺tála       | khan2016   | bpe       | ⁺, t, [UNK], la                 |
| ⁺tála       | khan2016   | unigram   | ⁺, t, á, la                     |
| ⁺tála       | khan2016   | wordpiece | ⁺, [UNK]                        |
| ⁺tála       | nazari2023 | bpe       | ⁺, t, [UNK], la                 |
| ⁺tála       | nazari2023 | unigram   | ⁺, t, á, la                     |
| ⁺tála       | nazari2023 | wordpiece | ⁺, [UNK]                        |

### Key Observations

- **General Performance:** All tokenizers struggled significantly with the morphological complexity of Neo-Aramaic. There was no clear superior dataset or tokenizer in this initial exploration.
- **Unigram Tokenizer:** This method often resulted in over-segmentation, breaking down words into too many small, uninformative parts.
- **Unknown Tokens:** The prevalence of unknown tokens ('[UNK]') across tokenizers, especially BPE and WordPiece, indicates a difficulty in handling rare or complex morphemes.

## Challenges and Limitations

One of the main challenges faced in this project was the inherent complexity of Neo-Aramaic's morphology, which proved problematic for all tested tokenization methods. The frequent appearance of unknown tokens suggests a need for more comprehensive training data or an adjustment in tokenizer configurations. Additionally, the constraints of working from a less-than-ideal environment and limited time impacted the depth of experimentation and analysis.

## Future Directions

Moving forward, the following steps are proposed to enhance the project:

1. **Data Enrichment:** Incorporating more diverse and extensive training data to better capture the linguistic diversity of Neo-Aramaic.
2. **Algorithmic Tweaks:** Modifying the tokenization algorithms to be more accommodating of the language's morphological features.
3. **Qualitative Analysis:** Conducting a more thorough qualitative assessment of each tokenizer's performance, possibly involving linguistic experts in Neo-Aramaic.
4. **Cross-linguistic Comparison:** Exploring tokenization in other morphologically rich languages to draw comparative insights and refine methodologies.

## Conclusion

This preliminary exploration into the tokenization of Neo-Aramaic highlights the challenges faced when dealing with morphologically complex languages. The findings underscore the need for continued research and tailored approaches in NLP for underrepresented languages. The insights gained here lay the groundwork for future advancements in this field.
