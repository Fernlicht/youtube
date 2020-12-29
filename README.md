# Tracking of YouTube views and subscribers

# Procedures

## Get channel views
1. Run ./updateStats.sh daily (in fact weekly would be sufficient).
2. Open ChannelViews.csv in Excel and copy the whole table to Excel/ChannelViews.xlsx::ViewsRaw (overwrite the whole sheet).
3. In tab ViewsDiff set End date to end of the week and Start date to beginning of the week (7d earlier).
4. Update the Pivot table in tab ViewsCh.

## Get channel subscribers
1. Run ./updateStats.sh daily (in fact weekly would be sufficient).
2. Open Subscribers.csv in Excel and copy the whole table to Excel/ChannelViews.xlsx::SubsRaw (overwrite the whole sheet).
3. In tab SubsDiff set End date to end of the week and Start date to beginning of the week (7d earlier).
4. Update the Pivot table in tab SubsCh.

## Get video views
1. Run ./updateVideoViews.sh. It takes around 30 min to complete.
1. Open Excel/VideoViews.xlsx.
1. Import VideoViews/VideoViews_YYYYMMDD.tsv configuring "Tabalutor" as separator. Configure the first column as "Text" instead of "Standard".
1. Rename the imported tab as YYYYMMDD.

# Data flow

## Input files
| **File**             | **Description** |
| -------------        | ------------- |
| channelIDs.txt       | YouTube channel IDs of the tracked channels.
| channelsByName.txt   | Legacy YouTube channel names instead of IDs.
| toBeAdded.txt        | Channel IDs to be added to the tracking.

## Output files
**File**             | **Description**
-------------        | -------------
ChannelViews.csv       |
Subscribers.csv        |
VideoViews.tsv         |

## Intermediate files
**File**             | **Description**
-------------        | -------------
playlistIds.txt      |
channelParams.txt    |

## Scripts
### extractChannelParam.sh
* <- channelIDs.txt
* <- channelsByName.txt
* -> channelParams.txt (new)
* -> playlistIds.txt (new)
* -> ChannelViews.csv (new)

### updateStats.sh
* <- channelParams.txt
* -> ChannelViews.csv
* -> Subscribers.csv

### updateVideoViews.sh
* <- playlistIds.txt
* -> VideoViews.csv
