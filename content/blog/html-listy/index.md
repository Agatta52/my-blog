---
title: HTML - listy
date: "2023-12-10T13:53:32.169Z"
description: "Jak zrobić listę? Listy: numerowane, punktowane, definicji i tabele."
slug: html-listy
---

### Lista numerowana

#### Kod
    <ol>
        <li>Element</li>
        <li>Element</li>
        <li>Element</li>
        <li>Element</li>
    </ol>

**Emmet:** `ol>li*4`
#### Wynik
1. Element
1. Element
1. Element
1. Element

### Lista punktowana

#### Kod
    <ul>
        <li>Element</li>
        <li>Element</li>
        <li>Element</li>
        <li>Element</li>
    </ul>

**Emmet:** `ul>li*4`
#### Wynik
* Element
* Element
* Element
* Element


### Lista definicji

#### Kod
    <dl> definition list
         <dt>definition term</dt>
         <dd>definition descripion</dd>
         <dt>definition term</dt>
         <dd>definition descripion</dd>
         <dt>definition term</dt>
         <dd>definition descripion</dd>
    </dl>

**Emmet:** `dl>(dt+dd)*3`
#### Wynik
<dl> definition list
    <dt>definition term</dt>
    <dd>definition descripion</dd>
    <dt>definition term</dt>
    <dd>definition descripion</dd>
    <dt>definition term</dt>
    <dd>definition descripion</dd>
</dl>


### Tabela

#### Kod
    <table>
    <caption>TABELA</caption>
    <thead>
        <tr>
            <th>Nagłówek 1.0</th>
            <th>Nagłówek 2.0</th>
            <th>Nagłówek 3.0</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Wartość 1.1</td>
            <td>Wartość 2.1</td>
            <td>Wartość 3.1</td>
        </tr>
        <tr>
            <td>Wartość 1.2</td>
            <td>Wartość 2.2</td>
            <td>Wartość 3.2</td>
        </tr>
    </tbody>
</table>

tr - table row

td - table data

th - table header

caption - podpis

#### Wynik
<table>
    <caption>TABELA</caption>
    <thead>
        <tr>
            <th>Nagłówek 1.0</th>
            <th>Nagłówek 2.0</th>
            <th>Nagłówek 3.0</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Wartość 1.1</td>
            <td>Wartość 2.1</td>
            <td>Wartość 3.1</td>
        </tr>
        <tr>
            <td>Wartość 1.2</td>
            <td>Wartość 2.2</td>
            <td>Wartość 3.2</td>
        </tr>
    </tbody>
</table>

#### Kod + (rozpiętość)
    <table>
    <caption></caption>
    <thead>
        <tr>
            <th colspan="2">Nagłówek 1.0 i 2.0</th>

            <th>Nagłówek 3.0</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Wartość 1.1</td>
            <td>Wartość 2.1</td>
            <td rowspan="2">Wartość 3.1 i 3.2</td>
        </tr>
        <tr>
            <td>Wartość 1.2</td>
            <td>Wartość 2.2</td>

        </tr>
    </tbody>
</table>
</table>


#### Wynik + (rozpiętość)
<table>
    <caption></caption>
    <thead>
        <tr>
            <th colspan="2">Nagłówek 1.0 i 2.0</th>
            <th>Nagłówek 3.0</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Wartość 1.1</td>
            <td>Wartość 2.1</td>
            <td rowspan="2">Wartość 3.1 i 3.2</td>
        </tr>
        <tr>
            <td>Wartość 1.2</td>
            <td>Wartość 2.2</td>
        </tr>
    </tbody>
</table>