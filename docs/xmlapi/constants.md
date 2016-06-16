# Response Data Constants
Constant values are used in certain response data columns to represent enumerated types.  These constants are defined in the tables below.

## Order State

<table border="1">
    <tbody>
        <tr>
            <th>Value</th>
            <th>Meaning</th>
        </tr>
        <tr>
            <td align="right">0</td>
            <td>Open or Active</td>
        </tr>
        <tr>
            <td align="right">1</td>
            <td>Closed</td>
        </tr>
        <tr>
            <td align="right">2</td>
            <td>Expired or Fulfilled</td>
        </tr>
        <tr>
            <td align="right">3</td>
            <td>Cancelled</td>
        </tr>
        <tr>
            <td align="right">4</td>
            <td>Pending</td>
        </tr>
        <tr>
            <td align="right">5</td>
            <td>Character Deleted</td>
        </tr>
    </tbody>
</table>

### Applies to
* [Character - MarketOrders](character/char_marketorders.md)
* [Corporation - MarketOrders](corporation/corp_marketorders.md)

## Order Range

<table border="1">
    <tbody>
        <tr>
            <th>Value</th>
            <th>Meaning</th>
        </tr>
        <tr>
            <td align="right">32767</td>
            <td>Region (buy order).  Default value for all sell orders.</td>
        </tr>
        <tr>
            <td align="right">-1</td>
            <td>Station (buy order)</td>
        </tr>
        <tr>
            <td align="right">0</td>
            <td>Solar System (buy order)</td>
        </tr>
        <tr>
            <td align="right">5, 10, 20, or 40</td>
            <td>Jumps from station where order was placed (buy order)</td>
        </tr>
    </tbody>
</table>

### Applies to
* [Character - MarketOrders](character/char_marketorders.md)
* [Corporation - MarketOrders](corporation/corp_marketorders.md)

## Raw Quantity

<table border="1">
    <tbody>
        <tr>
            <th>Value</th>
            <th>Meaning</th>
        </tr>
        <tr>
            <td align="right">-1</td>
            <td>Every item except blueprints: Singleton (=non-stackable)</td>
        </tr>
        <tr>
            <td align="right">-1</td>
            <td>Blueprint Original</td>
        </tr>
        <tr>
            <td align="right">-2</td>
            <td>Blueprint Copy</td>
        </tr>
    </tbody>
</table>

### Applies to
* [Character - AssetList](character/char_assetlist.md)
* [Corporation - AssetList](corporation/corp_assetlist.md)
* [Character - ContractItems](character/char_contractitems.md)
* [Corporation - ContractItems](corporation/corp_contractitems.md)

## Inventory Flags

These are the flags used by the inventory system. This data is available in the EVE SDE invFlags table.
They define hangars or slots where an item may reside. It should be noted that ingame items may have multiple flags, but the API will only show a single flag.


### Applies to
* [Character - AssetList](character/char_assetlist.md)
* [Character - Blueprints](character/char_blueprints.md)
* [Corporation - AssetList](corporation/corp_assetlist.md)
* [Character - Blueprints](corporation/corp_blueprints.md)

## Reference Type

<table border="1">
    <tbody>
        <tr>
            <th>refTypeID</th>
            <th>Name</th>
            <th>argName1</th>
            <th>argID1</th>
            <th>reason</th>
            <th>comment</th>
        </tr>
        <tr>
            <td align="right">1</td>
            <td>Player Trading</td>
            <td>Station name</td>
            <td>
                StationID
                <sup>
                <a href="../sde/mssql/mssql_staStations.html">[1]</a>
                </sup>
            </td>
            <td></td>
            <td>Location of direct player trade.  See <a href="../sde/mssql/mssql_staStations.html">Stations Table</a>.</td>
        </tr>
        <tr>
            <td align="right">2</td>
            <td>Market Transaction</td>
            <td>
                transactionID
                <sup>
                <a href="character/char_wallettransactions.html">[1]</a>
                <a href="corporation/corp_wallettransactions.html">[2]</a>
                </sup>
            </td>
            <td>0</td>
            <td></td>
            <td>See <a href="character/char_wallettransactions.html">Character - WalletTransactions</a> or <a href="corporation/corp_wallettransactions.html">Corporation - WalletTransactions</a>.</td>
        </tr>
        <tr>
            <td align="right">10</td>
            <td>Player Donation</td>
            <td></td>
            <td>0</td>
            <td>"DESC:" + player entered text</td>
            <td>Player donation with text entered by the donator appearing in the "reason" field.</td>
        </tr>
        <tr>
            <td align="right">17</td>
            <td>Bounty Prize (historical)</td>
            <td>NPC Name</td>
            <td>NPC ID</td>
            <td></td>
            <td>Relaced with refTypeID 85 in Trinity release.</td>
        </tr>
        <tr>
            <td align="right">19</td>
            <td>Insurance</td>
            <td>
                Destroyed Ship Type ID
                <sup>
                <a href="../sde/yaml/yaml_typeIDs.html">[1]</a>
                </sup>
            </td>
            <td>0</td>
            <td></td>
            <td>See <a href="../sde/yaml/yaml_typeIDs.html">Inventory Types file</a>.</td>
        </tr>
        <tr>
            <td align="right">35</td>
            <td>CONCORD Spam Prevention Act (CSPA)</td>
            <td>Player name</td>
            <td>Player character ID</td>
            <td></td>
            <td>Player name refers to the player you're trying to contact.</td>
        </tr>
        <tr>
            <td align="right">37</td>
            <td>Corp Account Withdrawal</td>
            <td>Player name that performed withdrawal</td>
            <td>Player character ID that performed withdrawal</td>
            <td>Player entered text</td>
            <td>Corp account withdrawal with text entered by the withdrawing player appearing in the "reason" field.</td>
        </tr>
        <tr>
            <td align="right">46</td>
            <td>Broker Fee</td>
            <td>EVE System</td>
            <td>1</td>
            <td></td>
            <td>Tags the market order commission fee for a market transaction.  The ownerName2 field indicates to whom the fee was paid.</td>
        </tr>
        <tr>
            <td align="right">56</td>
            <td>Manufacturing</td>
            <td>
                Job ID
                <sup>
                <a href="character/char_industryjobs.html">[1]</a>
                <a href="corporation/corp_industryjobs.html">[2]</a>
                </sup>
            </td>
            <td>0</td>
            <td></td>
            <td>Fee for industry manufacturing job.  See <a href="character/char_industryjobs.html">Character - IndustryJobs</a> or <a href="corporation/corp_industryjobs.html">Corporation - IndustryJobs</a>.</td>
        </tr>
        <tr>
            <td align="right">63, 64, 71, 72, 73, 74, 79, 80, 81, 82</td>
            <td>Various contract types</td>
            <td>Contract ID?</td>
            <td>0</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td align="right">85</td>
            <td>Bounty Prizes</td>
            <td></td>
            <td>
                solarSystemID
                <sup>
                <a href="../sde/sqlite/sqlite_mapSolarSystems.html" title="mapSolarSystems.solarSystemID">[1]</a>
                </sup>
            </td>
            <td>NPC ID:quantity killed[,id:qty[,...]]</td>
            <td>Arg1ID provides the solar system ID where the bounty was acquired.  For each type of NPC killed, its typeID is followed by a colon and the quantity killed. These pairs are seperated by commas, and if there are too many (more than about 60 characters' worth) the list is ended with a literal ",..." to indicate that more have been left off the list.</td>
        </tr>
        <tr>
            <td align="right">97</td>
            <td>Customs Office Export Duty</td>
            <td>Planet name</td>
            <td>
                Planet ID
                <sup>
                <a href="../sde/sqlite/sqlite_mapDenormalize.html" title="mapDenormalize.itemID">[1]</a>
                </sup>
            </td>
            <td>"Export Duty for " + planet name</td>
            <td>Customs office export duty for the named planet.  The duty was paid to the entity with ownerID2.</td>
        </tr>
    </tbody>
</table>

### Applies to
* [Character - WalletJournal](character/char_walletjournal.md)
* [Corporation - WalletJournal](corporation/corp_walletjournal.md)

## Notification Type

<table border="1">
    <tbody>
        <tr>
            <th>TypeID</th>
            <th>Description</th>
            <th>Structured Data</th>
        </tr>
        <tr>
            <td align="right">1</td>
            <td>Legacy</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">2</td>
            <td>Character deleted</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">3</td>
            <td>Give medal to character</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">4</td>
            <td>Alliance maintenance bill</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">5</td>
            <td>Alliance war declared</td>
            <td>againstID: 00000000<br>
                cost: 0<br>
                declaredByID: 00000001<br>
                delayHours: 24<br>
                hostileState: 1
            </td>
        </tr>
        <tr>
            <td align="right">6</td>
            <td>Alliance war surrender</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">7</td>
            <td>Alliance war retracted</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">8</td>
            <td>Alliance war invalidated by Concord</td>
            <td>againstID: 00000000<br>
                cost: null<br>
                declaredByID: 00000001<br>
                delayHours: null<br>
                hostileState: null
            </td>
        </tr>
        <tr>
            <td align="right">9</td>
            <td>Bill issued to a character</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">10</td>
            <td>Bill issued to corporation or alliance</td>
            <td>amount: 20000000<br>
                billTypeID: 2<br>
                creditorID: 00000000<br>
                currentDate: 130764012924912532<br>
                debtorID: 00000000<br>
                dueDate: 130789932230000000<br>
                externalID: 27<br>
                externalID2: 62300459
            </td>
            </tr>
        <tr>
            <td align="right">11</td>
            <td>Bill not paid because there's not enough ISK available</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">12</td>
            <td>Bill, issued by a character, paid</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">13</td>
            <td>Bill, issued by a corporation or alliance, paid</td>
            <td>amount: 25000000<br>
                dueDate: 130765575000000000
            </td>
        </tr>
        <tr>
            <td align="right">14</td>
            <td>Bounty claimed</td>
            <td>amount: 8508.5<br>
                charID: 90610935
            </td>
        </tr>
        <tr>
            <td align="right">15</td>
            <td>Clone activated</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">16</td>
            <td>New corp member application</td>
            <td>applicationText: 'hey there, let me join!'<br>
                charID: 90610935<br>
                corpID: 00000000
            </td>
        </tr>
        <tr>
            <td align="right">17</td>
            <td>Corp application rejected</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">18</td>
            <td>Corp application accepted</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">19</td>
            <td>Corp tax rate changed</td>
            <td>corpID: 00000000<br>
                newTaxRate: 0.10<br>
                oldTaxRate: 1.00
            </td>
        </tr>
        <tr>
            <td align="right">20</td>
            <td>Corp news report, typically for shareholders</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">21</td>
            <td>Player leaves corp</td>
	    <td>charID: 90610935<br>
                corpID: 00000000
	    </td>
        </tr>
        <tr>
            <td align="right">22</td>
            <td>Corp news, new CEO</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">23</td>
            <td>Corp dividend/liquidation, sent to shareholders</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">24</td>
            <td>Corp dividend payout, sent to shareholders</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">25</td>
            <td>Corp vote created</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">26</td>
            <td>Corp CEO votes revoked during voting</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">27</td>
            <td>Corp declares war</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">28</td>
            <td>Corp war has started</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">29</td>
            <td>Corp surrenders war</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">30</td>
            <td>Corp retracts war</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">31</td>
            <td>Corp war invalidated by Concord</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">32</td>
            <td>Container password retrieval</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">33</td>
            <td>Contraband or low standings cause an attack or items being confiscated</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">34</td>
            <td>First ship insurance</td>
	        <td>isHouseWarmingGift: 1<br>
                shipTypeID: 596
            </td>
        </tr>
        <tr>
            <td align="right">35</td>
            <td>Ship destroyed, insurance payed</td>
    	    <td>amount: 512304.80000000005<br>
                itemID: 1017375674103<br>
                payout: 1
            </td>
        </tr>
        <tr>
            <td align="right">36</td>
            <td>Insurance contract invalidated/runs out</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">37</td>
            <td>Sovereignty claim fails (alliance)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">38</td>
            <td>Sovereignty claim fails (corporation)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">39</td>
            <td>Sovereignty bill late (alliance)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">40</td>
            <td>Sovereignty bill late (corporation)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">41</td>
            <td>Sovereignty claim lost (alliance)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">42</td>
            <td>Sovereignty claim lost (corporation)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">43</td>
            <td>Sovereignty claim acquired (alliance)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">44</td>
            <td>Sovereignty claim acquired (corporation)</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">45</td>
            <td>Alliance anchoring alert</td>
			<td>allianceID: 00000000<br>
				corpID: 00000000<br>
				corpsPresent:<br>
				- allianceID: 00000000<br>
				&nbsp;&nbsp;corpID: 00000000<br>
				&nbsp;&nbsp;towers:<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 20062<br>
				- allianceID: 00000000<br>
				&nbsp;&nbsp;corpID: 00000000<br>
				&nbsp;&nbsp;towers:<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				- allianceID: 00000000<br>
				&nbsp;&nbsp;corpID: 00000000<br>
				&nbsp;&nbsp;towers:<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16213<br>
				- allianceID: 00000000<br>
				&nbsp;&nbsp;corpID: 00000000<br>
				&nbsp;&nbsp;towers:<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 27532<br>
				- allianceID: 00000000<br>
				&nbsp;&nbsp;corpID: 00000000<br>
				&nbsp;&nbsp;towers:<br>
				&nbsp;&nbsp;- moonID: 40009081<br>
				&nbsp;&nbsp;&nbsp;&nbsp;typeID: 16214<br>
				moonID: 40009081<br>
				solarSystemID: 30000142<br>
				typeID: 20064
			</td>
        </tr>
        <tr>
            <td align="right">46</td>
            <td>Alliance structure turns vulnerable</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">47</td>
            <td>Alliance structure turns invulnerable</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">48</td>
            <td>Sovereignty disruptor anchored</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">49</td>
            <td>Structure won/lost</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">50</td>
            <td>Corp office lease expiration notice</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">51</td>
            <td>Clone contract revoked by station manager</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">52</td>
            <td>Corp member clones moved between stations</td>
			<td>charsInCorpID: 90610935<br>
				corpID: 00000000<br>
				newStationID: 60000004<br>
				stationID: 60000007
			</td>
        </tr>
        <tr>
            <td align="right">53</td>
            <td>Clone contract revoked by station manager</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">54</td>
            <td>Insurance contract expired</td>
		    <td>endDate: 130739439920000000<br>
				shipID: 1015328647115<br>
				shipName: Tengu<br>
				startDate: 130666863920000000
			</td>
        </tr>
        <tr>
            <td align="right">55</td>
            <td>Insurance contract issued</td>
		    <td>endDate: 130837996425414355<br>
				itemID: 1018232075103<br>
				level: 99.99999999999999<br>
				numWeeks: 12<br>
				shipName: Ishtar<br>
				startDate: 130765420425414355<br>
				typeID: 12005
			</td>
        </tr>
        <tr>
            <td align="right">56</td>
            <td>Jump clone destroyed</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">57</td>
            <td>Jump clone destroyed</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">58</td>
            <td>Corporation joining factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">59</td>
            <td>Corporation leaving factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">60</td>
            <td>Corporation kicked from factional warfare on startup because of too low standing to the faction</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">61</td>
            <td>Character kicked from factional warfare on startup because of too low standing to the faction</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">62</td>
            <td>Corporation in factional warfare warned on startup because of too low standing to the faction</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">63</td>
            <td>Character in factional warfare warned on startup because of too low standing to the faction</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">64</td>
            <td>Character loses factional warfare rank</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">65</td>
            <td>Character gains factional warfare rank</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">66</td>
            <td>Agent has moved</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">67</td>
            <td>Mass transaction reversal message</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">68</td>
            <td>Reimbursement message</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">69</td>
            <td>Agent locates a character</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">70</td>
            <td>Research mission becomes available from an agent</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">71</td>
            <td>Agent mission offer expires</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">72</td>
            <td>Agent mission times out</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">73</td>
            <td>Agent offers a storyline mission</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">74</td>
            <td>Tutorial message sent on character creation</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">75</td>
            <td>Tower alert</td>
			<td>aggressorAllianceID: 00000000<br>
				aggressorCorpID: 00000000<br>
				aggressorID: 90610935<br>
				armorValue: 1.0<br>
				hullValue: 1.0<br>
				moonID: 40009081<br>
				shieldValue: 0.9999482233068171<br>
				solarSystemID: 30000142<br>
				typeID: 16213
			</td>
        </tr>
        <tr>
            <td align="right">76</td>
            <td>Tower resource alert</td>
		    <td>allianceID: 00000000<br>
				corpID: 00000000<br>
				moonID: 40009081<br>
				solarSystemID: 30000142<br>
				typeID: 20063<br>
				wants:<br>
				- quantity: 432<br>
				&nbsp;&nbsp;typeID: 4312<br>
			</td>
        </tr>
        <tr>
            <td align="right">77</td>
            <td>Station aggression message</td>
		    <td>aggressorCorpID: null<br>
				aggressorID: null<br>
				shieldValue: 0.9978610653837826<br>
				solarSystemID: 30000142<br>
				stationID: 60003757<br>
				typeID: 28156
			</td>
        </tr>
        <tr>
            <td align="right">78</td>
            <td>Station state change message</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">79</td>
            <td>Station conquered message</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">80</td>
            <td>Station aggression message</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">81</td>
            <td>Corporation requests joining factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">82</td>
            <td>Corporation requests leaving factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">83</td>
            <td>Corporation withdrawing a request to join factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">84</td>
            <td>Corporation withdrawing a request to leave factional warfare</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">85</td>
            <td>Corporation liquidation</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">86</td>
            <td>Territorial Claim Unit under attack</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">87</td>
            <td>Sovereignty Blockade Unit under attack</td>
		    <td>aggressorAllianceID: 00000000<br>
				aggressorCorpID: 00000000<br>
				aggressorID: 90610935<br>
				armorValue: 1.0<br>
				hullValue: 1.0<br>
				shieldValue: 0.999942577300314<br>
				solarSystemID: 30000142
			</td>
        </tr>
        <tr>
            <td align="right">88</td>
            <td>Infrastructure Hub under attack</td>
			<td>aggressorAllianceID: 00000000<br>
				aggressorCorpID: 00000000<br>
				aggressorID: 90610935<br>
				armorValue: 1.0<br>
				hullValue: 1.0<br>
				shieldValue: 0.9999601081022226<br>
				solarSystemID: 30000142
			</td>
        </tr>
        <tr>
            <td align="right">89</td>
            <td>Contact add notification</td>
	    <td>level: 10<br>
		message: Hi it was nice meeting you. I have set you blue.
	    </td>
        </tr>
        <tr>
            <td align="right">90</td>
            <td>Contact edit notification</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">91</td>
            <td>Incursion Completed</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">92</td>
            <td>Corp Kicked</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">93</td>
            <td>Customs office has been attacked</td>
		    <td>aggressorAllianceID: 00000000<br>
				aggressorCorpID: 00000000<br>
				aggressorID: 90610935<br>
				planetID: 40009081<br>
				planetTypeID: 2063<br>
				shieldLevel: 0.0<br>
				solarSystemID: 30000142<br>
				typeID: 2233
			</td>
        </tr>
        <tr>
            <td align="right">94</td>
            <td>Customs office has entered reinforced</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">95</td>
            <td>Customs office has been transferred</td>
		    <td>characterLinkData:<br>
				- showinfo<br>
				- 1375<br>
				- 90610935<br>
				characterName: CCP Guard<br>
				fromCorporationLinkData:<br>
				- showinfo<br>
				- 2<br>
				- 00000000<br>
				fromCorporationName: Foo Bar Corp<br>
				solarSystemLinkData:<br>
				- showinfo<br>
				- 5<br>
				- 30000142<br>
				solarSystemName: Jita<br>
				structureLinkData:<br>
				- showinfo<br>
				- 32226<br>
				- 1008433208457<br>
				structureName: Some random POCO<br>
				toCorporationLinkData:<br>
				- showinfo<br>
				- 2<br>
				- 00000001<br>
				toCorporationName: Bar Foo Corp
			</td>
        </tr>
        <tr>
            <td align="right">96</td>
            <td>FW Alliance Warning</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">97</td>
            <td>FW Alliance Kick</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">98</td>
            <td>AllWarCorpJoined Msg</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">99</td>
            <td>Ally Joined Defender</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">100</td>
            <td>Ally Has Joined a War Aggressor</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">101</td>
            <td>Ally Joined War Ally</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">102</td>
            <td>New war system: entity is offering assistance in a war.</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">103</td>
            <td>War Surrender Offer</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">104</td>
            <td>War Surrender Declined</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">105</td>
            <td>FacWar LP Payout Kill</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">106</td>
            <td>FacWar LP Payout Event</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">107</td>
            <td>FacWar LP Disqualified Eventd</td>
	    <td>TBD</td>
        </tr>
        <tr>
            <td align="right">108</td>
            <td>FacWar LP Disqualified Kill</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">109</td>
            <td>Alliance Contract Cancelled</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">110</td>
            <td>War Ally Declined Offer</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">111</td>
            <td>Your Bounty Was Claimed</td>
            <td>bounty: 11111.0<br>
		victimID: 00000000
	    </td>
        </tr>
        <tr>
            <td align="right">112</td>
            <td>Bounty placed (Char)</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">113</td>
            <td>Bounty Placed (Corp)</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">114</td>
            <td>Bounty Placed (Alliance)</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">115</td>
            <td>Kill Right Available</td>
            <td>charID: 00000000<br>
		price: 0.0<br>
		toEntityID: 00000000
	    </td>
        </tr>
        <tr>
            <td align="right">116</td>
            <td>Kill right Available Open</td>
            <td>charID: 00000000<br>
		price: 0.0
	    </td>
        </tr>
        <tr>
            <td align="right">117</td>
            <td>Kill Right Earned</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">118</td>
            <td>Kill right Used</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">119</td>
            <td>Kill Right Unavailable</td>
            <td>charID: 00000000<br>
		toEntityID: 00000000
	    </td>
        </tr>
        <tr>
            <td align="right">120</td>
            <td>Kill Right Unavailable Open</td>
            <td>charID: 00000000</td>
        </tr>
        <tr>
            <td align="right">121</td>
            <td>Declare War</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">122</td>
            <td>Offered Surrender</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">123</td>
            <td>Accepted Surrender</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">124</td>
            <td>Made War Mutual</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">125</td>
            <td>Retracts War</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">126</td>
            <td>Offered To Ally</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">127</td>
            <td>Accepted Ally</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">128</td>
            <td>Character Application Accept</td>
            <td>applicationText: Hey, this is my alt.<br>
                charID: 900000000<br>
                corpID: 000000001
            </td>
        </tr>
        <tr>
            <td align="right">129</td>
            <td>Character Application Reject</td>
            <td>TBD</td>
        </tr>
        <tr>
            <td align="right">130</td>
            <td>Character Application Withdraw</td>
            <td>applicationText: Hey, this is my alt.<br>
		charID: 900000000<br>
		corpID: 000000001
            </td>
        </tr>
        <tr>
            <td align="right">138</td>
            <td>Clone activated</td>
            <td>cloneStationID: 60000000<br>
                corpStationID: 60000001<br>
                lastCloned: 130975015800000000<br>
                podKillerID: 100000000
            </td>
        </tr>
        <tr>
            <td align="right">140</td>
            <td>Loss report available</td>
            <td>killMailHash: aaf4c61ddcc5e8a2dabede0f3b482cd9aea9434d<br>
                killMailID: 00000000<br>
                victimShipTypeID: 596
            </td>
        </tr>
        <tr>
            <td align="right">141</td>
            <td>Kill report available</td>
            <td>killMailHash: a415ab5cc17c8c093c015ccdb7e552aee7911aa4<br>
                killMailID: 00000000<br>
                victimID: 000000001<br>
                victimShipTypeID: 596
            </td>
        </tr>
        <tr>
            <td align="right">147</td>
            <td>Entosis Link started</td>
            <td>solarSystemID: 30000142<br>
                structureTypeID: 28159
            </td>
        </tr>
        <tr>
            <td align="right">148</td>
            <td>Entosis Link enabled a module</td>
            <td>solarSystemID: 30000142<br>
                structureTypeID: 28159
            </td>
        </tr>
        <tr>
            <td align="right">149</td>
            <td>Entosis Link disabled a module</td>
            <td>solarSystemID: 30000142<br>
				structureTypeID: 28159
			</td>
        </tr>
    </tbody>
</table>

### Applies to
* [Character - Notifications](character/char_notifications.md)

## Known POS States
<table border="1">
        <tbody>
            <tr>
                <th>State</th>
                <th>Name</th>
                <th>Notes</th>
            </tr>
            <tr>
                <td align="right">0</td>
                <td>Unanchored</td>
                <td>Also unanchoring? Has valid stateTimestamp. Note that moonID is zero for unanchored Towers, but locationID will still yield the solar system ID.</td>
            </tr>
            <tr>
                <td align="right">1</td>
                <td>Anchored / Offline</td>
                <td>No time information stored.</td>
            </tr>
            <tr>
                <td align="right">2</td>
                <td>Onlining</td>
                <td>Will be online at time = onlineTimestamp.</td>
            </tr>
            <tr>
                <td align="right">3</td>
                <td>Reinforced</td>
                <td>Until time = stateTimestamp.</td>
            </tr>
            <tr>
                <td align="right">4</td>
                <td>Online</td>
                <td>Continuously since time = onlineTimestamp.</td>
            </tr>
        </tbody>
    </table>

### Applies to
* [Corporation - StarbaseList](corporation/corp_starbaselist.md)
* [Corporation - StarbaseDetail](corporation/corp_starbasedetail.md)

## Industry Job Status

<table border="1">
    <tbody>
        <tr>
            <th>Value</th>
            <th>Meaning</th>
        </tr>
        <tr>
            <td align="right">1</td>
            <td>Installed</td>
        </tr>
        <tr>
            <td align="right">2</td>
            <td>Paused/Facility Offline</td>
        </tr>
        <tr>
            <td align="right">3</td>
            <td>Ready</td>
        </tr>
        <tr>
            <td align="right">101</td>
            <td>Delivered</td>
        </tr>
        <tr>
            <td align="right">102</td>
            <td>Cancelled</td>
        </tr>
        <tr>
            <td align="right">103</td>
            <td>Reverted</td>
        </tr>
        <tr>
            <td align="right">104</td>
            <td>Succeeded</td>
        </tr>
        <tr>
            <td align="right">105</td>
            <td>Failed</td>
        </tr>
    </tbody>
</table>

### Applies to
* [Character - IndustryJobs](character/char_industryjobs.md)
* [Character - IndustryJobsHistory](character/char_industryjobshistory.md)
* [Corporation - IndustryJobs](corporation/corp_industryjobs.md)
* [Corporation - IndustryJobsHistory](corporation/corp_industryjobshistory.md)

