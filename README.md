# Paasaa

[![Travis](https://img.shields.io/travis/minibikini/paasaa.svg?maxAge=2592000)](https://travis-ci.org/minibikini/paasaa)
[![Coverage Status](https://coveralls.io/repos/github/minibikini/paasaa/badge.svg?branch=master)](https://coveralls.io/github/minibikini/paasaa?branch=master)
[![Hex.pm](https://img.shields.io/hexpm/v/paasaa.svg?maxAge=2592000)](https://hex.pm/packages/paasaa)
[![Hex.pm](https://img.shields.io/hexpm/l/paasaa.svg?maxAge=2592000)](https://hex.pm/packages/paasaa)

Natural language detection for Elixir. Built with support for 187 languages (1M or more speakers).

## Features

- When other ports return just ISO-639-3 codes, Paasaa additionally returns ISO-639-2B, ISO-639-2T, ISO-639-1 and language name (when available);
- Battle-proven algorithm and data that are based on [Franc][] and ported to number of other languages;
- 100% test coverage. Test suite checks recognition for text translated to 187 languages;
- minimum number of dependencies (just Jason).

[Api Documentation] | [Hex Package]

## Installation

Add `paasaa` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [{:paasaa, "~> 1.0.0"}]
end
```

After you are done, run `mix deps.get` in your shell to fetch and compile **Paasaa**.

## Usage

Detect a language:

```elixir
iex> Paasaa.detect("Detect this!")
{:ok, %Paasaa.Language{
  iso6393: "eng",
  name: "English",
  iso6391: "en",
  iso6392B: "eng",
  iso6392T: "eng",
  scope: "individual",
  type: "living"
}}
```

Detect language and return a scored list of languages:

```elixir
iex> Paasaa.all("Detect this!")
[
  {"eng", 1.0},
  {"sco", 0.8668304668304668},
  {"nob", 0.6054054054054054},
  {"swe", 0.5921375921375922},
  {"nno", 0.5518427518427518}
  ...
]
```

## Derivation

**Paasaa** is a derivative work from [Franc][] (JavaScript, MIT) by [Titus Wormer].

## Language Support

This build supports the following languages:

| Code | Name | Speakers |
| ---- | ---- | -------- |
| [`cmn`](http://www-01.sil.org/iso639-3/documentation.asp?id=cmn) | Mandarin Chinese | 885M |
| [`spa`](http://www-01.sil.org/iso639-3/documentation.asp?id=spa) | Spanish | 332M |
| [`eng`](http://www-01.sil.org/iso639-3/documentation.asp?id=eng) | English | 322M |
| [`rus`](http://www-01.sil.org/iso639-3/documentation.asp?id=rus) | Russian | 288M |
| [`arb`](http://www-01.sil.org/iso639-3/documentation.asp?id=arb) | Standard Arabic | 280M |
| [`ben`](http://www-01.sil.org/iso639-3/documentation.asp?id=ben) | Bengali | 196M |
| [`hin`](http://www-01.sil.org/iso639-3/documentation.asp?id=hin) | Hindi | 182M |
| [`por`](http://www-01.sil.org/iso639-3/documentation.asp?id=por) | Portuguese | 182M |
| [`ind`](http://www-01.sil.org/iso639-3/documentation.asp?id=ind) | Indonesian | 140M |
| [`jpn`](http://www-01.sil.org/iso639-3/documentation.asp?id=jpn) | Japanese | 125M |
| [`fra`](http://www-01.sil.org/iso639-3/documentation.asp?id=fra) | French | 124M |
| [`deu`](http://www-01.sil.org/iso639-3/documentation.asp?id=deu) | German | 121M |
| [`jav`](http://www-01.sil.org/iso639-3/documentation.asp?id=jav) | Javanese | 76M |
| [`kor`](http://www-01.sil.org/iso639-3/documentation.asp?id=kor) | Korean | 75M |
| [`tel`](http://www-01.sil.org/iso639-3/documentation.asp?id=tel) | Telugu | 73M |
| [`vie`](http://www-01.sil.org/iso639-3/documentation.asp?id=vie) | Vietnamese | 67M |
| [`mar`](http://www-01.sil.org/iso639-3/documentation.asp?id=mar) | Marathi | 65M |
| [`ita`](http://www-01.sil.org/iso639-3/documentation.asp?id=ita) | Italian | 63M |
| [`tam`](http://www-01.sil.org/iso639-3/documentation.asp?id=tam) | Tamil | 62M |
| [`tur`](http://www-01.sil.org/iso639-3/documentation.asp?id=tur) | Turkish | 59M |
| [`urd`](http://www-01.sil.org/iso639-3/documentation.asp?id=urd) | Urdu | 54M |
| [`guj`](http://www-01.sil.org/iso639-3/documentation.asp?id=guj) | Gujarati | 44M |
| [`pol`](http://www-01.sil.org/iso639-3/documentation.asp?id=pol) | Polish | 44M |
| [`ukr`](http://www-01.sil.org/iso639-3/documentation.asp?id=ukr) | Ukrainian | 41M |
| [`fas`](http://www-01.sil.org/iso639-3/documentation.asp?id=fas) | Persian | 40M |
| [`kan`](http://www-01.sil.org/iso639-3/documentation.asp?id=kan) | Kannada | 38M |
| [`mai`](http://www-01.sil.org/iso639-3/documentation.asp?id=mai) | Maithili | 35M |
| [`mal`](http://www-01.sil.org/iso639-3/documentation.asp?id=mal) | Malayalam | 34M |
| [`mya`](http://www-01.sil.org/iso639-3/documentation.asp?id=mya) | Burmese | 31M |
| [`ori`](http://www-01.sil.org/iso639-3/documentation.asp?id=ori) | Oriya (macrolanguage) | 31M |
| [`gax`](http://www-01.sil.org/iso639-3/documentation.asp?id=gax) | Borana-Arsi-Guji Oromo | 30M |
| [`swh`](http://www-01.sil.org/iso639-3/documentation.asp?id=swh) | Swahili (individual language) | 30M |
| [`sun`](http://www-01.sil.org/iso639-3/documentation.asp?id=sun) | Sundanese | 27M |
| [`ron`](http://www-01.sil.org/iso639-3/documentation.asp?id=ron) | Romanian | 26M |
| [`pan`](http://www-01.sil.org/iso639-3/documentation.asp?id=pan) | Panjabi | 26M |
| [`bho`](http://www-01.sil.org/iso639-3/documentation.asp?id=bho) | Bhojpuri | 25M |
| [`amh`](http://www-01.sil.org/iso639-3/documentation.asp?id=amh) | Amharic | 23M |
| [`hau`](http://www-01.sil.org/iso639-3/documentation.asp?id=hau) | Hausa | 22M |
| [`fuv`](http://www-01.sil.org/iso639-3/documentation.asp?id=fuv) | Nigerian Fulfulde | 22M |
| [`bos`](http://www-01.sil.org/iso639-3/documentation.asp?id=bos) | Bosnian (Cyrillic) | 21M |
| [`bos`](http://www-01.sil.org/iso639-3/documentation.asp?id=bos) | Bosnian (Latin) | 21M |
| [`hrv`](http://www-01.sil.org/iso639-3/documentation.asp?id=hrv) | Croatian | 21M |
| [`nld`](http://www-01.sil.org/iso639-3/documentation.asp?id=nld) | Dutch | 21M |
| [`srp`](http://www-01.sil.org/iso639-3/documentation.asp?id=srp) | Serbian (Cyrillic) | 21M |
| [`srp`](http://www-01.sil.org/iso639-3/documentation.asp?id=srp) | Serbian (Latin) | 21M |
| [`tha`](http://www-01.sil.org/iso639-3/documentation.asp?id=tha) | Thai | 21M |
| [`ckb`](http://www-01.sil.org/iso639-3/documentation.asp?id=ckb) | Central Kurdish | 20M |
| [`yor`](http://www-01.sil.org/iso639-3/documentation.asp?id=yor) | Yoruba | 20M |
| [`uzn`](http://www-01.sil.org/iso639-3/documentation.asp?id=uzn) | Northern Uzbek (Cyrillic) | 18M |
| [`uzn`](http://www-01.sil.org/iso639-3/documentation.asp?id=uzn) | Northern Uzbek (Latin) | 18M |
| [`zlm`](http://www-01.sil.org/iso639-3/documentation.asp?id=zlm) | Malay (individual language) (Arabic) | 18M |
| [`zlm`](http://www-01.sil.org/iso639-3/documentation.asp?id=zlm) | Malay (individual language) (Latin) | 18M |
| [`ibo`](http://www-01.sil.org/iso639-3/documentation.asp?id=ibo) | Igbo | 17M |
| [`nep`](http://www-01.sil.org/iso639-3/documentation.asp?id=nep) | Nepali (macrolanguage) | 16M |
| [`ceb`](http://www-01.sil.org/iso639-3/documentation.asp?id=ceb) | Cebuano | 15M |
| [`skr`](http://www-01.sil.org/iso639-3/documentation.asp?id=skr) | Saraiki | 15M |
| [`tgl`](http://www-01.sil.org/iso639-3/documentation.asp?id=tgl) | Tagalog | 15M |
| [`hun`](http://www-01.sil.org/iso639-3/documentation.asp?id=hun) | Hungarian | 15M |
| [`azj`](http://www-01.sil.org/iso639-3/documentation.asp?id=azj) | North Azerbaijani (Cyrillic) | 14M |
| [`azj`](http://www-01.sil.org/iso639-3/documentation.asp?id=azj) | North Azerbaijani (Latin) | 14M |
| [`sin`](http://www-01.sil.org/iso639-3/documentation.asp?id=sin) | Sinhala | 13M |
| [`koi`](http://www-01.sil.org/iso639-3/documentation.asp?id=koi) | Komi-Permyak | 13M |
| [`ell`](http://www-01.sil.org/iso639-3/documentation.asp?id=ell) | Modern Greek (1453-) | 12M |
| [`ces`](http://www-01.sil.org/iso639-3/documentation.asp?id=ces) | Czech | 12M |
| [`run`](http://www-01.sil.org/iso639-3/documentation.asp?id=run) | Rundi | 11M |
| [`bel`](http://www-01.sil.org/iso639-3/documentation.asp?id=bel) | Belarusian | 10M |
| [`plt`](http://www-01.sil.org/iso639-3/documentation.asp?id=plt) | Plateau Malagasy | 10M |
| [`qug`](http://www-01.sil.org/iso639-3/documentation.asp?id=qug) | Chimborazo Highland Quichua | 10M |
| [`mad`](http://www-01.sil.org/iso639-3/documentation.asp?id=mad) | Madurese | 10M |
| [`nya`](http://www-01.sil.org/iso639-3/documentation.asp?id=nya) | Nyanja | 10M |
| [`zyb`](http://www-01.sil.org/iso639-3/documentation.asp?id=zyb) | Yongbei Zhuang | 10M |
| [`pbu`](http://www-01.sil.org/iso639-3/documentation.asp?id=pbu) | Northern Pashto | 10M |
| [`kin`](http://www-01.sil.org/iso639-3/documentation.asp?id=kin) | Kinyarwanda | 9M |
| [`zul`](http://www-01.sil.org/iso639-3/documentation.asp?id=zul) | Zulu | 9M |
| [`bul`](http://www-01.sil.org/iso639-3/documentation.asp?id=bul) | Bulgarian | 9M |
| [`swe`](http://www-01.sil.org/iso639-3/documentation.asp?id=swe) | Swedish | 9M |
| [`lin`](http://www-01.sil.org/iso639-3/documentation.asp?id=lin) | Lingala | 8M |
| [`som`](http://www-01.sil.org/iso639-3/documentation.asp?id=som) | Somali | 8M |
| [`hms`](http://www-01.sil.org/iso639-3/documentation.asp?id=hms) | Southern Qiandong Miao | 8M |
| [`hnj`](http://www-01.sil.org/iso639-3/documentation.asp?id=hnj) | Hmong Njua | 8M |
| [`ilo`](http://www-01.sil.org/iso639-3/documentation.asp?id=ilo) | Iloko | 8M |
| [`kaz`](http://www-01.sil.org/iso639-3/documentation.asp?id=kaz) | Kazakh | 8M |
| [`uig`](http://www-01.sil.org/iso639-3/documentation.asp?id=uig) | Uighur (Arabic) | 7M |
| [`uig`](http://www-01.sil.org/iso639-3/documentation.asp?id=uig) | Uighur (Latin) | 7M |
| [`hat`](http://www-01.sil.org/iso639-3/documentation.asp?id=hat) | Haitian | 7M |
| [`khm`](http://www-01.sil.org/iso639-3/documentation.asp?id=khm) | Khmer | 7M |
| [`aka`](http://www-01.sil.org/iso639-3/documentation.asp?id=aka) | Akan | 7M |
| [`hil`](http://www-01.sil.org/iso639-3/documentation.asp?id=hil) | Hiligaynon | 7M |
| [`sna`](http://www-01.sil.org/iso639-3/documentation.asp?id=sna) | Shona | 7M |
| [`tat`](http://www-01.sil.org/iso639-3/documentation.asp?id=tat) | Tatar | 7M |
| [`xho`](http://www-01.sil.org/iso639-3/documentation.asp?id=xho) | Xhosa | 7M |
| [`hye`](http://www-01.sil.org/iso639-3/documentation.asp?id=hye) | Armenian | 7M |
| [`min`](http://www-01.sil.org/iso639-3/documentation.asp?id=min) | Minangkabau | 7M |
| [`afr`](http://www-01.sil.org/iso639-3/documentation.asp?id=afr) | Afrikaans | 6M |
| [`lua`](http://www-01.sil.org/iso639-3/documentation.asp?id=lua) | Luba-Lulua | 6M |
| [`sat`](http://www-01.sil.org/iso639-3/documentation.asp?id=sat) | Santali | 6M |
| [`bod`](http://www-01.sil.org/iso639-3/documentation.asp?id=bod) | Tibetan | 6M |
| [`tir`](http://www-01.sil.org/iso639-3/documentation.asp?id=tir) | Tigrinya | 6M |
| [`fin`](http://www-01.sil.org/iso639-3/documentation.asp?id=fin) | Finnish | 6M |
| [`slk`](http://www-01.sil.org/iso639-3/documentation.asp?id=slk) | Slovak | 6M |
| [`tuk`](http://www-01.sil.org/iso639-3/documentation.asp?id=tuk) | Turkmen (Cyrillic) | 5M |
| [`tuk`](http://www-01.sil.org/iso639-3/documentation.asp?id=tuk) | Turkmen (Latin) | 5M |
| [`dan`](http://www-01.sil.org/iso639-3/documentation.asp?id=dan) | Danish | 5M |
| [`nob`](http://www-01.sil.org/iso639-3/documentation.asp?id=nob) | Norwegian Bokmål | 5M |
| [`suk`](http://www-01.sil.org/iso639-3/documentation.asp?id=suk) | Sukuma | 5M |
| [`als`](http://www-01.sil.org/iso639-3/documentation.asp?id=als) | Tosk Albanian | 5M |
| [`sag`](http://www-01.sil.org/iso639-3/documentation.asp?id=sag) | Sango | 5M |
| [`nno`](http://www-01.sil.org/iso639-3/documentation.asp?id=nno) | Norwegian Nynorsk | 5M |
| [`heb`](http://www-01.sil.org/iso639-3/documentation.asp?id=heb) | Hebrew | 5M |
| [`mos`](http://www-01.sil.org/iso639-3/documentation.asp?id=mos) | Mossi | 5M |
| [`tgk`](http://www-01.sil.org/iso639-3/documentation.asp?id=tgk) | Tajik | 4M |
| [`cat`](http://www-01.sil.org/iso639-3/documentation.asp?id=cat) | Catalan | 4M |
| [`sot`](http://www-01.sil.org/iso639-3/documentation.asp?id=sot) | Southern Sotho | 4M |
| [`kat`](http://www-01.sil.org/iso639-3/documentation.asp?id=kat) | Georgian | 4M |
| [`bcl`](http://www-01.sil.org/iso639-3/documentation.asp?id=bcl) | Central Bikol | 4M |
| [`glg`](http://www-01.sil.org/iso639-3/documentation.asp?id=glg) | Galician | 4M |
| [`lao`](http://www-01.sil.org/iso639-3/documentation.asp?id=lao) | Lao | 4M |
| [`lit`](http://www-01.sil.org/iso639-3/documentation.asp?id=lit) | Lithuanian | 4M |
| [`umb`](http://www-01.sil.org/iso639-3/documentation.asp?id=umb) | Umbundu | 4M |
| [`tsn`](http://www-01.sil.org/iso639-3/documentation.asp?id=tsn) | Tswana | 4M |
| [`vec`](http://www-01.sil.org/iso639-3/documentation.asp?id=vec) | Venetian | 4M |
| [`nso`](http://www-01.sil.org/iso639-3/documentation.asp?id=nso) | Pedi | 4M |
| [`ban`](http://www-01.sil.org/iso639-3/documentation.asp?id=ban) | Balinese | 4M |
| [`bug`](http://www-01.sil.org/iso639-3/documentation.asp?id=bug) | Buginese | 4M |
| [`knc`](http://www-01.sil.org/iso639-3/documentation.asp?id=knc) | Central Kanuri | 4M |
| [`kng`](http://www-01.sil.org/iso639-3/documentation.asp?id=kng) | Koongo | 3M |
| [`ibb`](http://www-01.sil.org/iso639-3/documentation.asp?id=ibb) | Ibibio | 3M |
| [`lug`](http://www-01.sil.org/iso639-3/documentation.asp?id=lug) | Ganda | 3M |
| [`ace`](http://www-01.sil.org/iso639-3/documentation.asp?id=ace) | Achinese | 3M |
| [`bam`](http://www-01.sil.org/iso639-3/documentation.asp?id=bam) | Bambara | 3M |
| [`tzm`](http://www-01.sil.org/iso639-3/documentation.asp?id=tzm) | Central Atlas Tamazight | 3M |
| [`ydd`](http://www-01.sil.org/iso639-3/documentation.asp?id=ydd) | Eastern Yiddish | 3M |
| [`kmb`](http://www-01.sil.org/iso639-3/documentation.asp?id=kmb) | Kimbundu | 3M |
| [`lun`](http://www-01.sil.org/iso639-3/documentation.asp?id=lun) | Lunda | 3M |
| [`shn`](http://www-01.sil.org/iso639-3/documentation.asp?id=shn) | Shan | 3M |
| [`war`](http://www-01.sil.org/iso639-3/documentation.asp?id=war) | Waray (Philippines) | 3M |
| [`dyu`](http://www-01.sil.org/iso639-3/documentation.asp?id=dyu) | Dyula | 3M |
| [`wol`](http://www-01.sil.org/iso639-3/documentation.asp?id=wol) | Wolof | 3M |
| [`kir`](http://www-01.sil.org/iso639-3/documentation.asp?id=kir) | Kirghiz | 3M |
| [`nds`](http://www-01.sil.org/iso639-3/documentation.asp?id=nds) | Low German | 3M |
| [`fuf`](http://www-01.sil.org/iso639-3/documentation.asp?id=fuf) | Pular | 3M |
| [`mkd`](http://www-01.sil.org/iso639-3/documentation.asp?id=mkd) | Macedonian | 3M |
| [`vmw`](http://www-01.sil.org/iso639-3/documentation.asp?id=vmw) | Makhuwa | 3M |
| [`zgh`](http://www-01.sil.org/iso639-3/documentation.asp?id=zgh) | Standard Moroccan Tamazight | 2M |
| [`ewe`](http://www-01.sil.org/iso639-3/documentation.asp?id=ewe) | Ewe | 2M |
| [`khk`](http://www-01.sil.org/iso639-3/documentation.asp?id=khk) | Halh Mongolian | 2M |
| [`slv`](http://www-01.sil.org/iso639-3/documentation.asp?id=slv) | Slovenian | 2M |
| [`ayr`](http://www-01.sil.org/iso639-3/documentation.asp?id=ayr) | Central Aymara | 2M |
| [`bem`](http://www-01.sil.org/iso639-3/documentation.asp?id=bem) | Bemba (Zambia) | 2M |
| [`emk`](http://www-01.sil.org/iso639-3/documentation.asp?id=emk) | Eastern Maninkakan | 2M |
| [`bci`](http://www-01.sil.org/iso639-3/documentation.asp?id=bci) | Baoulé | 2M |
| [`bum`](http://www-01.sil.org/iso639-3/documentation.asp?id=bum) | Bulu (Cameroon) | 2M |
| [`epo`](http://www-01.sil.org/iso639-3/documentation.asp?id=epo) | Esperanto | 2M |
| [`pam`](http://www-01.sil.org/iso639-3/documentation.asp?id=pam) | Pampanga | 2M |
| [`tiv`](http://www-01.sil.org/iso639-3/documentation.asp?id=tiv) | Tiv | 2M |
| [`tpi`](http://www-01.sil.org/iso639-3/documentation.asp?id=tpi) | Tok Pisin | 2M |
| [`ven`](http://www-01.sil.org/iso639-3/documentation.asp?id=ven) | Venda | 2M |
| [`ssw`](http://www-01.sil.org/iso639-3/documentation.asp?id=ssw) | Swati | 2M |
| [`nyn`](http://www-01.sil.org/iso639-3/documentation.asp?id=nyn) | Nyankole | 2M |
| [`kbd`](http://www-01.sil.org/iso639-3/documentation.asp?id=kbd) | Kabardian | 2M |
| [`iii`](http://www-01.sil.org/iso639-3/documentation.asp?id=iii) | Sichuan Yi | 2M |
| [`yao`](http://www-01.sil.org/iso639-3/documentation.asp?id=yao) | Yao | 2M |
| [`lav`](http://www-01.sil.org/iso639-3/documentation.asp?id=lav) | Latvian | 2M |
| [`quz`](http://www-01.sil.org/iso639-3/documentation.asp?id=quz) | Cusco Quechua | 2M |
| [`src`](http://www-01.sil.org/iso639-3/documentation.asp?id=src) | Logudorese Sardinian | 2M |
| [`sco`](http://www-01.sil.org/iso639-3/documentation.asp?id=sco) | Scots | 2M |
| [`tso`](http://www-01.sil.org/iso639-3/documentation.asp?id=tso) | Tsonga | 2M |
| [`rmy`](http://www-01.sil.org/iso639-3/documentation.asp?id=rmy) | Vlax Romani | 2M |
| [`men`](http://www-01.sil.org/iso639-3/documentation.asp?id=men) | Mende (Sierra Leone) | 1M |
| [`fon`](http://www-01.sil.org/iso639-3/documentation.asp?id=fon) | Fon | 1M |
| [`nhn`](http://www-01.sil.org/iso639-3/documentation.asp?id=nhn) | Central Nahuatl | 1M |
| [`dip`](http://www-01.sil.org/iso639-3/documentation.asp?id=dip) | Northeastern Dinka | 1M |
| [`kde`](http://www-01.sil.org/iso639-3/documentation.asp?id=kde) | Makonde | 1M |
| [`snn`](http://www-01.sil.org/iso639-3/documentation.asp?id=snn) | Siona | 1M |
| [`kbp`](http://www-01.sil.org/iso639-3/documentation.asp?id=kbp) | Kabiyè | 1M |
| [`tem`](http://www-01.sil.org/iso639-3/documentation.asp?id=tem) | Timne | 1M |
| [`toi`](http://www-01.sil.org/iso639-3/documentation.asp?id=toi) | Tonga (Zambia) | 1M |
| [`est`](http://www-01.sil.org/iso639-3/documentation.asp?id=est) | Estonian | 1M |
| [`snk`](http://www-01.sil.org/iso639-3/documentation.asp?id=snk) | Soninke | 1M |
| [`cjk`](http://www-01.sil.org/iso639-3/documentation.asp?id=cjk) | Chokwe | 1M |
| [`ada`](http://www-01.sil.org/iso639-3/documentation.asp?id=ada) | Adangme | 1M |
| [`aii`](http://www-01.sil.org/iso639-3/documentation.asp?id=aii) | Assyrian Neo-Aramaic | 1M |
| [`quy`](http://www-01.sil.org/iso639-3/documentation.asp?id=quy) | Ayacucho Quechua | 1M |
| [`rmn`](http://www-01.sil.org/iso639-3/documentation.asp?id=rmn) | Balkan Romani | 1M |
| [`bin`](http://www-01.sil.org/iso639-3/documentation.asp?id=bin) | Bini | 1M |
| [`gaa`](http://www-01.sil.org/iso639-3/documentation.asp?id=gaa) | Ga | 1M |
| [`ndo`](http://www-01.sil.org/iso639-3/documentation.asp?id=ndo) | Ndonga | 1M |

## License

[MIT] © [Egor Kislitsyn]

<!-- Definitions -->

[Api Documentation]: https://hexdocs.pm/paasaa/Paasaa.html
[Hex Package]: https://hex.pm/packages/paasaa
[Franc]: https://github.com/wooorm/franc/
[Titus Wormer]: http://wooorm.com/
[mit]: LICENSE
[Egor Kislitsyn]: https://github.com/minibikini
