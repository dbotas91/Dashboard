---
tags:
  - others
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
# Example - DON'T DELETE BEFORE DOING A CSV MERGE

|   |   |
|---|---|
|![](Dashboard/Attachments/list_gray%201056.svg)Tags||
|![](Dashboard/Attachments/checkmark-square_gray%20786.svg)Gathered||
|![](Dashboard/Attachments/checkmark-square_gray%20786.svg)In Video||
|![](Dashboard/Attachments/checkmark-square_gray%20786.svg)Premiere||

If you don't care about the magical benefits of CSV merges, then just use this area to manually create a list of B-roll shots.

---

If you use [Frame.io](http://frame.io) to create comments on your video's rough A-Roll cut, either for fixes or B-roll ideas, you can export all those comments to a CSV file.

Then you can go into Google Sheets and delete all columns except for the Comment and Timestamp ones.

Leave the top row with the column names - Notion has a bug (not fixed yet) that will randomly delete one of your rows on CSV import. However, I've found that if you leave that top row there, it'll always delete that one.

I have no idea why this happens, but it does.

Download your new, 2-column CSV file and do a CSV merge on this B-roll table (well, not this one - duplicate this entire row in the Master Tracker and then do it on the B-roll table there). Again, make sure you don't delete this item before the merge - it's the only thing that will preserve all the useful columns here. Without it, the CSV will delete all columns here and replace them with the two that it has. But with it, it'll just import perfectly.

From there, you can start adding tags to each B-roll item. Why do this? Well, each tag is a "gather type". By assigning gather types, such as "film" or "online image", you can batch your b-roll gathering tasks. It's the same idea that filmmakers use when shooting scenes: If Scenes A, B, H, and Z are all in the same location, they'll shoot them altogether even if they separated by other scenes in the final movie cut. Batching makes you more productive.

Once you're done tagging, use the various database views for each stage of the project. Switch to Gather first to sort everything by Gather Type. Once you're done collecting, you can go back to Chrono, which makes it easy for you (or your editor) to zoom right to the timestamp in the video and place B-roll.

Use Fix view to show any entry with "#fix" in its content. I use this for A-roll fixes that need to be done.

Finally, you can use the Premiere checkbox and switch between Premiere and After Effects views if you're like me and work with both Premiere and After Effects.