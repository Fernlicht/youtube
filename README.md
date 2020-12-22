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
1. Make a backup of VideoViews.tsv.
1. Remove the whole content after <<VideoID	URL	"Title"	"Channel">>.
1. Close VideoViews.tsv in the IDE / editor (its getting big and will be updated many times).
1. Run ./updateVideoViews.sh. It takes around 30 min to complete.
