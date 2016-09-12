# WalletJournal
Retrieve character wallet journal.

* __Path:__ ``/char/WalletJournal.xml.aspx``
* __Cache timer:__ 30 minutes
* __Access mask:__ 2097152
* __Parameters:__
    <table border="1">
        <tbody>
            <tr>
                <th>Argument</th>
                <th>Type</th>
                <th>Description</th>
            </tr>
            <tr>
                <td>characterID</td>
                <td><strong>long</strong></td>
                <td>Character ID for which journal entries will be requested</td>
            </tr>
            <tr>
                <td>accountKey</td>
                <td><strong>int</strong></td>
                <td>
                Account key of the wallet for which journal entries will be returned.  This is optional for character accounts which only have one wallet (accountKey = 1000).
                However, corporations have seven wallets with accountKeys numbered from 1000 through 1006.  The <a href="../corporation/corp_accountbalance.html">Corporation - AccountBalance</a> 
                call can be used to map corporation wallet to appropriate accountKey.
                </td>
            </tr>
            <tr>
                <td>fromID</td>
                <td><strong>long</strong></td>
                <td>
                Optional upper bound for the ref ID of returned journal entries.  This argument is normally used to walk to the journal backwards.
                See <a href="../intro.html#journal-walking">Journal Walking</a> for more information.
                </td>
            </tr>
            <tr>
                <td>rowCount</td>
                <td><strong>int</strong></td>
                <td>
                Optional limit on number of rows to return.  Default is 1000.  Maximum is 2560.
                </td>
            </tr>
        </tbody>
    </table>

### Sample Response

```xml
<result>
    <rowset name="transactions" key="refID" columns="date,refID,refTypeID,ownerName1,ownerID1,ownerName2,ownerID2,argName1,argID1,amount,balance,reason,taxReceiverID,taxAmount">
        <row date="2012-12-16 14:47:03" refID="6709813912" refTypeID="15" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="Wiyrkomi Corporation" ownerID2="1000011" argName1="EVE System" argID1="1" amount="-9250.00" balance="385574791.30" reason="" taxReceiverID="" taxAmount="" />
        <row date="2012-12-15 18:53:29" refID="6705533817" refTypeID="97" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="CONCORD" ownerID2="1000125" argName1="Vorsk VI" argID1="40215551" amount="-206000.00" balance="385584041.30" reason="Export Duty for Vorsk VI" taxReceiverID="" taxAmount="" />
        <row date="2012-12-15 18:53:05" refID="6705532062" refTypeID="97" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="CONCORD" ownerID2="1000125" argName1="Vorsk III" argID1="40215546" amount="-254000.00" balance="385790041.30" reason="Export Duty for Vorsk III" taxReceiverID="" taxAmount="" />
        <row date="2012-12-15 18:52:38" refID="6705529857" refTypeID="97" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="CONCORD" ownerID2="1000125" argName1="Vorsk II" argID1="40215545" amount="-160000.00" balance="386044041.30" reason="Export Duty for Vorsk II" taxReceiverID="" taxAmount="" />
        <row date="2012-12-15 18:51:50" refID="6705526089" refTypeID="97" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="CONCORD" ownerID2="1000125" argName1="Vorsk I" argID1="40215544" amount="-183000.00" balance="386204041.30" reason="Export Duty for Vorsk I" taxReceiverID="" taxAmount="" />
        <row date="2012-12-13 10:37:13" refID="6694409579" refTypeID="15" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="Wiyrkomi Corporation" ownerID2="1000011" argName1="EVE System" argID1="1" amount="-21275.00" balance="386387041.30" reason="" taxReceiverID="" taxAmount="" />
        <row date="2012-12-13 01:02:16" refID="6692943658" refTypeID="97" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="CONCORD" ownerID2="1000125" argName1="Vorsk VI" argID1="40215551" amount="-259000.00" balance="386408316.30" reason="Export Duty for Vorsk VI" taxReceiverID="" taxAmount="" />
        <row date="2012-12-13 01:01:32" refID="6692941689" refTypeID="97" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="CONCORD" ownerID2="1000125" argName1="Vorsk III" argID1="40215546" amount="-317000.00" balance="386667316.30" reason="Export Duty for Vorsk III" taxReceiverID="" taxAmount="" />
        <row date="2012-12-13 01:01:24" refID="6692941373" refTypeID="97" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="CONCORD" ownerID2="1000125" argName1="Vorsk II" argID1="40215545" amount="-171000.00" balance="386984316.30" reason="Export Duty for Vorsk II" taxReceiverID="" taxAmount="" />
        <row date="2012-12-13 01:00:37" refID="6692939153" refTypeID="97" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="CONCORD" ownerID2="1000125" argName1="Vorsk I" argID1="40215544" amount="-248000.00" balance="387155316.30" reason="Export Duty for Vorsk I" taxReceiverID="" taxAmount="" />
        <row date="2012-11-22 12:49:07" refID="6607375119" refTypeID="97" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="CONCORD" ownerID2="1000125" argName1="Vorsk II" argID1="40215545" amount="-213000.00" balance="446826716.30" reason="Export Duty for Vorsk II" taxReceiverID="" taxAmount="" />
        <row date="2012-11-22 12:48:59" refID="6607374952" refTypeID="97" ownerName1="reygar burnt" ownerID1="1801683792" ownerName2="CONCORD" ownerID2="1000125" argName1="Vorsk I" argID1="40215544" amount="-228000.00" balance="447039716.30" reason="Export Duty for Vorsk I" taxReceiverID="" taxAmount="" />
    </rowset>
</result>
```

### Result Data

<table border="1">
    <tbody>
        <tr>
            <td>transactions</td>
            <td><strong>rowset</strong></td>
            <td></td>
            <td>Rowset containing 1 row per journal entry.</td>
        </tr>
        <tr>
            <td></td>
            <td>date</td>
            <td><strong>datetime</strong></td>
            <td>Date and time of transaction.</td>
        </tr>
        <tr>
            <td></td>
            <td>refID</td>
            <td><strong>long</strong></td>
            <td>Unique journal reference ID.</td>
        </tr>
        <tr>
            <td></td>
            <td>refTypeID</td>
            <td>
                <strong>int</strong>
                <sup>
                    <a href="../constants.html#reference-type">[1]</a>
                    <a href="../eve/eve_reftypes.html">[2]</a>
                </sup>
            </td>
            <td>Transaction type.</td>
        </tr>
        <tr>
            <td></td>
            <td>ownerName1</td>
            <td><strong>string</strong></td>
            <td>Name of first party in transaction.</td>
        </tr>
        <tr>
            <td></td>
            <td>ownerID1</td>
            <td>
                <strong>long</strong>
                <sup>
                    <a href="../../sde/mssql/mssql_crpNPCCorporations.html" title="NPC Corporations table when first party is an NPC Corporation">[1]</a>
                </sup>
            </td>
            <td>Character or corporation ID of first party.  For NPC corporations, see the appropriate cross reference.</td>
        </tr>
        <tr>
            <td></td>
            <td>ownerName2</td>
            <td><strong>string</strong></td>
            <td>Name of second party in transaction.</td>
        </tr>
        <tr>
            <td></td>
            <td>ownerID2</td>
            <td>
                <strong>long</strong>
                <sup>
                    <a href="../../sde/mssql/mssql_crpNPCCorporations.html" title="NPC Corporations table when second party is an NPC Corporation">[1]</a>
                </sup>
            </td>
            <td>Character or corporation ID of second party.  For NPC corporations, see the appropriate cross reference.</td>
        </tr>
        <tr>
            <td></td>
            <td>argName1</td>
            <td><strong>variable</strong></td>
            <td>Ref type dependent argument name.  See the <a href="../constants.html#reference-type">Reference Type table</a>.</td>
        </tr>
        <tr>
            <td></td>
            <td>argID1</td>
            <td>
                <strong>int</strong>
            </td>
            <td>Ref type dependent argument value.  See the <a href="../constants.html#reference-type">Reference Type table</a>.</td>
        </tr>
        <tr>
            <td></td>
            <td>amount</td>
            <td><strong>decimal</strong></td>
            <td>Transaction amount.  Positive when value transferred to the first owner.  Negative otherwise.</td>
        </tr>
        <tr>
            <td></td>
            <td>balance</td>
            <td><strong>decimal</strong></td>
            <td>Wallet balance after transaction occurred.</td>
        </tr>
        <tr>
            <td></td>
            <td>reason</td>
            <td><strong>string</strong></td>
            <td>Ref type dependent reason.  See the <a href="../constants.html#reference-type">Reference Type table</a>.</td>
        </tr>
        <tr>
            <td></td>
            <td>taxReceiverID</td>
            <td>
                <strong>long</strong>
                <sup>
                    <a href="../../sde/mssql/mssql_crpNPCCorporations.html" title="NPC Corporations table when tax receiver is an NPC Corporation">[1]</a>
                </sup>
            </td>
            <td>For tax related transactions, gives the corporation ID of the entity receiving the tax.</td>
        </tr>
        <tr>
            <td></td>
            <td>taxAmount</td>
            <td>
                <strong>decimal</strong>
            </td>
            <td>Tax amount received for tax related transactions.</td>
        </tr>
    </tbody>
</table>

### References

* [refTypeID list](../constants#reference-type)
* [Old EVE Online forums thread about refID](http://oldforums.eveonline.com/?a=topic&threadID=764508)
* [CCP Prism X talks journal walking on the old forums](http://oldforums.eveonline.com/?a=topic&threadID=1453360&page=2#60)
* [CCP Stillman talks journal fixes in the Incursion 1.4 patch notes](http://oldforums.eveonline.com/?a=topic&threadID=1490703)
