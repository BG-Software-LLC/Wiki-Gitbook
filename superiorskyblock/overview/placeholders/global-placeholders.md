---
description: Placeholders that are not related to a specific island or player.
---

# Global Placeholders

### superior\_island\_total\_count

Get the total count of islands on the server.

#### Example Output

3,400

### superior\_island\_total\_count\_format

Get the total count of islands on the server formatted.

#### Example Output

3.4K

### superior\_island\_total\_count\_raw

Get the total count of islands on the server in raw format.

#### Example Output

3400

### superior\_island\_total\_level

Get the total island-levels of all islands.

#### Example Output

1,900,000.00

### superior\_island\_total\_level\_format

Get the total island-levels of all islands formatted.

#### Example Output

1.9M

### superior\_island\_total\_level\_int

Get the total island-levels of all islands as an integer.

#### Example Output

1900000

### superior\_island\_total\_level\_raw

Get the total island-levels of all islands in raw format.

#### Example Output

1900000.00

### superior\_island\_total\_worth

Get the total worth-value of all islands.

#### Example Output

1,900,000.00

### superior\_island\_total\_worth\_format

Get the total worth-value of all islands formatted.

#### Example Output

1.9M

### superior\_island\_total\_worth\_int

Get the total worth-value of all islands as an integer.

#### Example Output

1900000

### superior\_island\_total\_worth\_raw

Get the total worth-value of all islands in raw format.

#### Example Output

1900000.00

{% hint style="info" %}
The default sorting types available are: `bank`, `level`, `players`, `rating` and `worth`.\
You can register your own sorting-types using [API](https://wiki.bg-software.com/superiorskyblock/overview/api).
{% endhint %}

### superior\_island\_top\_\<sorting-type>\_<#>

Get the name of an island in a specific place sorted by sorting-type.

#### Parameters

\<sorting-type>: The sorting type used to sort the islands.

_<#>_: The position of the island to get, ranging from 1.

#### Example Usage

`superior_island_top_worth_1`

### superior\_island\_top\_\<sorting-type>\_value\_<#>

Get the value of an island in a specific place sorted by sorting-type.

#### Parameters

\<sorting-type>: The sorting type used to sort the islands.

_<#>_: The position of the island to get, ranging from 1.

#### Example Usage

`superior_island_top_worth_1`

### superior\_island\_top\_\<sorting-type>\_leader\_<#>

Get the leader's name of an island in a specific place sorted by sorting-type.

#### Parameters

\<sorting-type>: The sorting type used to sort the islands.

_<#>_: The position of the island to get, ranging from 1.

#### Example Usage

`superior_island_top_worth_leader_1`

### superior\_island\_top\_\<sorting-type>\_<#>\_\<placeholder>

Run a placeholder on an island in a specific place sorted by sorting-type.

#### Parameters

\<sorting-type>: The sorting type used to sort the islands.

_<#>_: The position of the island to get, ranging from 1.

\<placeholder>: The placeholder to run.

#### Example Usage

`superior_island_top_worth_1_bank_limit`
