{% comment %}
This file is licensed under the MIT License (MIT) available on
http://opensource.org/licenses/MIT.
{% endcomment %}
{% assign filename="_includes/devdoc/dash-core/rpcs/rpcs/getaddressbalance.md" %}

##### GetAddressBalance
{% include helpers/subhead-links.md %}

{% autocrossref %}

{% assign summary_getAddressBalance="returns the balance for address(es)." %}

*Requires wallet support and `-addressindex` Lifetioncoin Core command-line/configuration-file parameter to be enabled.*

The `getaddressbalance` RPC {{summary_getAddressBalance}}

*Parameter #1---an array of addresses*

{% itemplate ntpd1 %}
- n: "`addresses`"
  t: "object"
  p: "Required<br>(exactly 1)"
  d: "An array of P2PKH or P2SH Lifetioncoin address(es)"

- n: "→Address"
  t: "string (base58)"
  p: "Required<br>(1 or more)"
  d: "The base58check encoded address"

{% enditemplate %}

*Result---the current balance in duffs and the total number of duffs received (including change)*

{% itemplate ntpd1 %}
- n: "`result`"
  t: "object"
  p: "Required<br>(exactly 1)"
  d: "An object listing the current balance and total amount received (including change), or an error if any address is invalid"

- n: "→<br>`balance`"
  t: "string"
  p: "Required<br>(exactly 1)"
  d: "The current balance in duffs"

- n: "→<br>`received`"
  t: "string"
  p: "Required<br>(exactly 1)"
  d: "The total number of duffs received (including change)"

{% enditemplate %}

*Example from Lifetioncoin Core 0.12.2*

Get the balance for an address:

{% highlight bash %}
dash-cli getaddressbalance '{"addresses": ["yWjoZBvnUKWhpKMbBkVVnnMD8Bzno9j6tQ"]}'
{% endhighlight %}

Result:

{% highlight json %}
{
  "balance": 0,
  "received": 10000100
}
{% endhighlight %}

*See also*

* [GetBalance][rpc getbalance]: {{summary_getBalance}}
* [GetUnconfirmedBalance][rpc getunconfirmedbalance]: {{summary_getUnconfirmedBalance}}

{% endautocrossref %}
