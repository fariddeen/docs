


# Transfer Action

A Token Owner(s) Sends, Excahnges or Swaps a token(s) or Bitcoin for a token(s) or Bitcoin.  Can be as simple as sending a single token to a receiver.  Or can be as complex as many senders sending many different assets - controlled by many different smart contracts - to a number of receivers.  This action also supports atomic swaps (tokens for tokens).  Since many parties and contracts can be involved in a transfer and the corresponding settlement action, the partially signed T1 and T2 actions will need to be passed around on-chain with an M1 action, or off-chain.

The following breaks down the construction of a Transfer Action. The action is constructed by building a single string from each of the elements in order.

<div class="ritz grid-container" dir="ltr">
    <table class="waffle" cellspacing="0" cellpadding="0" table-layout=fixed width=100%>
         <tr style='height:19px;'>
            <th style="width:9%" class="s0">Label</th>
            <th style="width:9%" class="s1">Name</th>
            <th style="width:2%" class="s1">Bytes</th>
            <th style="width:25%" class="s1">Example Values</th>
            <th style="width:36%" class="s1">Comments</th>
            <th style="width:5%" class="s1">Data Type</th>
            <th class="s1">Amendment Restrictions</th>
        </tr>
        <tr>
            <td class="t5" colspan="7">
                <a href="javascript:;" data-popover="type-Header">
                   Header - Click to show content
                </a>
             </td>
        </tr>
        <tr>
            <td class="t9">Asset Count</td>
            <td class="t10">AssetTransferCount</td>
            <td class="t10">1</td>
            <td class="t10">0</td>
            <td class="t10">The number of Asset Transfers involved in this Transfer Action.</td>
            <td class="t10">uint8</td>
            <td class="t10"></td>
        </tr>
        <tr>
            <td class="t5" colspan="7">
                <a href="javascript:;" data-popover="type-AssetTransfer">
                   Assets - Click to show content
                </a>
            </td>
        </tr>
        <tr>
            <td class="t9">Offer Expiry</td>
            <td class="t10">OfferExpiry</td>
            <td class="t10">8</td>
            <td class="t10"><abbr title="Sun May 06 2018 06:00:00 GMT+1000 (AEST)">Hover for example</abbr></td>
            <td class="t10"><abbr title="This prevents any party from holding on to the partially signed message as a form of an option.  Eg. the exchange at this price is valid for 30 mins.">This prevents any party from holding on to the partially signed message as a form of an op ...</abbr></td>
            <td class="t10">time</td>
            <td class="t10"></td>
        </tr>
        <tr>
            <td class="t9">Exchange Fee Currency</td>
            <td class="t10">ExchangeFeeCurrency</td>
            <td class="t10">3</td>
            <td class="t10">AUD</td>
            <td class="t10">BSV, USD, AUD, EUR, etc.</td>
            <td class="t10">string</td>
            <td class="t10"></td>
        </tr>
        <tr>
            <td class="t9">Exchange Fee Variable</td>
            <td class="t10">ExchangeFeeVar</td>
            <td class="t10">4</td>
            <td class="t10">0.005</td>
            <td class="t10">Percent of the value of the transaction</td>
            <td class="t10">float32</td>
            <td class="t10"></td>
        </tr>
        <tr>
            <td class="t9">Exchange Fee Fixed</td>
            <td class="t10">ExchangeFeeFixed</td>
            <td class="t10">4</td>
            <td class="t10">0.01</td>
            <td class="t10">Fixed fee</td>
            <td class="t10">float32</td>
            <td class="t10"></td>
        </tr>
        <tr>
            <td class="t9">Exchange Fee Address</td>
            <td class="t10">ExchangeFeeAddress</td>
            <td class="t10">34</td>
            <td class="t10"><abbr title="1HQ2ULuD7T5ykaucZ3KmTo4i29925Qa6ic">Hover for example</abbr></td>
            <td class="t10">Identifies the public address that the exchange fee should be paid to.</td>
            <td class="t10">string</td>
            <td class="t10"></td>
        </tr>
    </table>
</div>

##Transfer Action Transaction Summary

<div class="ritz grid-container" dir="ltr">
    <table class="waffle" cellspacing="0" cellpadding="0" table-layout=fixed width=100%>
         <tr style='height:19px;'>
            <th class="s0" colspan="6">Smart Contract Operator Fee: 0</th>
       </tr>
         <tr style='height:19px;'>
            <th style="width:10%" class="s0">Index (input)</th>
            <th style="width:20%" class="s1">Txn inputs</th>
            <th style="width:20%" class="s1">Comments</th>
            <th style="width:10%" class="s1">Index (output)</th>
            <th style="width:20%" class="s1">Txn outputs</th>
            <th class="s1">Comments</th>
       </tr>
       <tr>
            <td class="t5">[{AssetXSenderX Asset (token) Sending Public Address X }]</td>
            <td class="t6">.</td>
            <td class="t6">.</td>
            <td class="t10">.</td>
            <td class="t10">.</td>
            <td class="t10">.</td>
        </tr>
    </table>
</div>



<div class="ui modal" id="type-Header">
    <i class="close icon"></i>
    <div class="content docs-content">
        <table class="ui table">
            <tr style='height:19px;'>
                <th style="width:5%" class="s1">Label</th>
                <th style="width:9%" class="s1">Name</th>
                <th style="width:3%" class="s1">Bytes</th>
                <th style="width:33%" class="s1">Example Values</th>
                <th style="width:26%" class="s1">Comments</th>
                <th style="width:5%" class="s1">Data Type</th>
                <th class="s2">Amendment Restrictions</th>
            </tr>
            <tr>
                <td class="t10">Protocol Identifier</td>
                <td class="t10">ProtocolID</td>
                <td class="t10">13</td>
                <td class="t10" style="word-break:break-all">tokenized.com</td>
                <td class="t10">Tokenized ID Prefix.  tokenized.com</td>
                <td class="t10">string</td>
                <td class="t10"></td>
            </tr>
            <tr>
                <td class="t10">Push Data</td>
                <td class="t10">OpPushdata</td>
                <td class="t10">1</td>
                <td class="t10" style="word-break:break-all">77</td>
                <td class="t10">PACKET LENGTH, PUSHDATA1 (76), PUSHDATA2 (77), or PUSHDATA4 (78) depending on total size of action payload.</td>
                <td class="t10">opcode</td>
                <td class="t10">Cannot be changed by issuer, operator or smart contract.</td>
            </tr>
            <tr>
                <td class="t10">Length of Action Payload</td>
                <td class="t10">LenActionPayload</td>
                <td class="t10">2</td>
                <td class="t10" style="word-break:break-all">409</td>
                <td class="t10">Length of the action message (0 - 65,535 bytes). 0 if pushdata length <76B, 1 byte if PUSHDATA1 is used, 2 bytes if PUSHDATA2 and 4 bytes if PUSHDATA4.</td>
                <td class="t10">pushdata_length</td>
                <td class="t10">Depends on Action Payload</td>
            </tr>
            <tr>
                <td class="t10">Version</td>
                <td class="t10">Version</td>
                <td class="t10">1</td>
                <td class="t10" style="word-break:break-all">0</td>
                <td class="t10">255 reserved for additional versions. Tokenized protocol versioning.</td>
                <td class="t10">uint8</td>
                <td class="t10">Can be changed by Issuer or Operator at their discretion.  Smart Contract will reject if it hasn't been updated to interpret the specified version.</td>
            </tr>
            <tr>
                <td class="t10">Action Prefix</td>
                <td class="t10">ActionPrefix</td>
                <td class="t10">2</td>
                <td class="t10" style="word-break:break-all">T1</td>
                <td class="t10">// T1 identifies data as a Transfer message.</td>
                <td class="t10">string</td>
                <td class="t10">Cannot be changed by issuer, operator or smart contract.</td>
            </tr>
        </table>
    </div>
</div>

<div class="ui modal" id="type-AssetTransfer">
    <i class="close icon"></i>
    <div class="content docs-content">
        <table class="ui table">
            <tr style='height:19px;'>
                <th style="width:5%" class="s1">Label</th>
                <th style="width:9%" class="s1">Name</th>
                <th style="width:3%" class="s1">Bytes</th>
                <th style="width:33%" class="s1">Example Values</th>
                <th style="width:26%" class="s1">Comments</th>
                <th style="width:5%" class="s1">Data Type</th>
                <th class="s2">Amendment Restrictions</th>
            </tr>
            <tr>
                <td class="t10">Asset Type</td>
                <td class="t10">Type</td>
                <td class="t10">3</td>
                <td class="t10" style="word-break:break-all">SHC</td>
                <td class="t10">eg. Share, Bond, Ticket. All characters must be capitalised.</td>
                <td class="t10">string</td>
                <td class="t10"></td>
            </tr>
            <tr>
                <td class="t10">Asset ID</td>
                <td class="t10">ID</td>
                <td class="t10">32</td>
                <td class="t10" style="word-break:break-all">apm2qsznhks23z8d83u41s8019hyri3i</td>
                <td class="t10">Randomly generated base58 string.  Each Asset ID should be unique.  However, a Asset ID is always linked to a Contract that is identified by the public address of the Contract wallet. The Asset Type can be the leading bytes - a convention - to make it easy to identify that it is a token by humans.</td>
                <td class="t10">string</td>
                <td class="t10"></td>
            </tr>
            <tr>
                <td class="t10">Token Sender Count</td>
                <td class="t10">SenderCount</td>
                <td class="t10">1</td>
                <td class="t10" style="word-break:break-all">0</td>
                <td class="t10">Number inputs sending tokens. 1-255, 0 is not valid.</td>
                <td class="t10">uint8</td>
                <td class="t10"></td>
            </tr>
            <tr>
                <td class="t10">Senders</td>
                <td class="t10">Senders</td>
                <td class="t10">0</td>
                <td class="t10" style="word-break:break-all"></td>
                <td class="t10">Each element has the value of tokens to be spent from the input address, which is referred to by the index.</td>
                <td class="t10">QuantityIndex[]</td>
                <td class="t10"></td>
            </tr>
            <tr>
                <td class="t10">The number of token receivers</td>
                <td class="t10">ReceiverCount</td>
                <td class="t10">1</td>
                <td class="t10" style="word-break:break-all">0</td>
                <td class="t10">Number of outputs receiving tokens. 1-255. 0 is not valid.</td>
                <td class="t10">uint8</td>
                <td class="t10"></td>
            </tr>
            <tr>
                <td class="t10">Receivers</td>
                <td class="t10">Receivers</td>
                <td class="t10">0</td>
                <td class="t10" style="word-break:break-all"></td>
                <td class="t10">Each element has the value of tokens to be received by the output address, which is referred to by the index.</td>
                <td class="t10">TokenReceiver[]</td>
                <td class="t10"></td>
            </tr>
        </table>
    </div>
</div>
