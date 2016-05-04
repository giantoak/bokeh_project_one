# bokeh_project_one
Messing with demo data from &lt;People> to make a cool viz.

## Assorted possibly-useful analysis libraries
Things we could throw at the data to perhaps produce something useful. *NOT* something necessarily more useful than

* [skl-groups](https://dougalsutherland.github.io/skl-groups/tutorial.html) for clusters of text documents with identical authors.

* [MIT-LL's pLSA topic clustering](https://github.com/mitll/topic-clustering) To get a topic model of prominent text themes. Always handy as a way for showing relationships between documents. (Newman incorporates MIT's pLSA tools)

* *If* we have a particular type of document that we'd like to identify [ActiveSearch](https://github.com/AutonlabCMU/ActiveSearch) would be useful when we spend some time classifying stuff.

* [NILS](https://github.com/plamenbbn/XDATA.git) isn’t explained clearly enough to understand whether it’s very clever or (more likely) a replication of some sort of network calculation already in iGraph. Could be easy fodder for a network viz.

* [snap.py](http://snap.stanford.edu/snappy/) and [igraph](http://igraph.org/redirect.html) both include a lot of network analytics written in C and with python front ends, so if we want to calculate networks stats on any FERC data we can use either one. Since snap.py doesn't support python 3 I'm inclined towards igraph, but either is fine. The SNAP group at Stanford is kind of hot.

* We could try to use [Blaze](http://blaze.pydata.org/) as a drop-in substitute for pandas. It's kind of clunky still, but should make it easier to work with the data interactively while on disk.

## Assorted possibly-useful visualization platforms
* Use [VizLinc](https://github.com/mitll/vizlinc) instead of / in addition to Newman? Another let's-find-insight-in-text tool that we could toss the raw data into.

* [UpSet](https://github.com/VCG/upset) visualization of different entity characteristics? We'd need to consider what sort of set relationships we might find in-between the different documents

* [Neon](https://github.com/NextCenturyCorporation/neon) is yet another one-size-fits-all text analysis dashboard. It might also be worth an ingest.

* [Bokeh](http://bokeh.pydata.org/en/latest/) is less a platform than a particular visualization library, but that's honestly better. Let's stick with the examples, turn off interactivity unless we really want it, and call that that.

## Some candidate workflows:
1. Dump data into SQLite / SQL / something so that it gets a bit preprocessed.
2. Use blaze and dask to do some parallel processing of data frames to generate new fields
3. Render the results.

1. Dump data into neon
2. Visualize it, get some insights.

1. Generate some relational sets.
2. Put the data into UpSet.

## Things I'd like from Sotera
Ingest of all the data into Newman!


## Random call notes

* "need to stick to the established model" (Database, GUI, etc.)
* Mike wants to represent the volume of emails across multiple targets the goal
* Want to stick with the XDATA catalog?

* Why not Newman?
  * several issues with getting full-featured stuff out of the XDATA catalog.
    * need to find out if something is full featured
    * we're biting off a big support challenge if we choose to use something.
  * outlook messages are super compressed.

* According to Hugh, Sotera will deal with ingesting the data into Newman.

"Not a lot of data if it's to, from, and count"

1. elastic for the messages
2. igraph / snappy to turn elastic messages into graphs
3. Tangelo working with loaded graph data.
