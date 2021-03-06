{% comment %}
This file is licensed under the MIT License (MIT) available on
http://opensource.org/licenses/MIT.
{% endcomment %}
{% assign filename="_includes/devdoc/dash-core/rpcs/rpcs/getnewaddress.md" %}

##### GetNewAddress
{% include helpers/subhead-links.md %}

{% assign summary_getNewAddress="returns a new Lifetioncoin address for receiving payments. If an account is specified, payments received with the address will be credited to that account." %}

<!-- __ -->

{% autocrossref %}

*Requires wallet support.*

The `getnewaddress` RPC {{summary_getNewAddress}}

*Parameter #1---an account name*

{% itemplate ntpd1 %}
- n: "Account"
  t: "string"
  p: "Optional<br>(0 or 1)"
  d: "The name of the account to put the address in.  The default is the default account, an empty string (\"\")"

{% enditemplate %}

*Result---a dash address never previously returned*

{% itemplate ntpd1 %}
- n: "`result`"
  t: "string (base58)"
  p: "Required<br>(exactly 1)"
  d: "A P2PKH address which has not previously been returned by this RPC.  The address will be marked as a receiving address in the wallet.  The address may already have been part of the keypool, so other RPCs such as the `dumpwallet` RPC may have disclosed it previously.  If the wallet is unlocked, its keypool will also be filled to its max (by default, 100 unused keys).  If the wallet is locked and its keypool is empty, this RPC will fail"

{% enditemplate %}

*Example from Lifetioncoin Core 0.12.2*

Create a new address in the "doc test" account:

{% highlight bash %}
dash-cli -testnet getnewaddress "doc test"
{% endhighlight %}

Result:

{% highlight text %}
yPuNTqCGzXtU3eEV5jHvhhJkzEPyJLmVkb
{% endhighlight %}

*See also*

* [GetAccountAddress][rpc getaccountaddress]: {{summary_getAccountAddress}}
* [GetRawChangeAddress][rpc getrawchangeaddress]: {{summary_getRawChangeAddress}}
* [GetBalance][rpc getbalance]: {{summary_getBalance}}

{% endautocrossref %}
