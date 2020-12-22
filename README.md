# Tracking of YouTube views and subscribers

# Procedures
## Get channel views
Procedure:
1. Run ./updateStats.sh daily (in fact weekly would be sufficient).
2. Open ChannelViews.csv in Excel and copy the whole table to Excel/ChannelViews.xlsx::ViewsRaw (overwrite the whole sheet).
3. In tab ViewsDiff set End date to end of the week and Start date to beginning of the week (7d earlier).
4. Update the Pivot table in tab ViewsCh.
## Get channel subscribers
