# dbp_wn_mapping

This git is part of new Clustering-Based unsupervised AKE system called SemCluster. The full code and documentation paper is to appear soon.


# What is this ?

The following hierarchy represents an alignment of DBPedia knowledgebase schema (http://mappings.dbpedia.org/server/ontology/classes/) against WordNet (v.3.1) nouns category (viewed as ontology).

During alignment, each DBPedia datatype class is mapped to its exact or semantically equivalent synset in WordNet (i.e. Noun sense), therefore, there are classes mapped directly, whereas others mapped roughly.


# Why its useful ?

The main advantage of such alignment is to provide a way of WordNet-based ontological linking between two DBPedia entries, or between a WordNet entry and a DBPedia entry, hence allowing to measure the semantic similarity between any given pair of nouns among which at least one noun is not available in WordNet. As side effect of this alignment, a system relies on WordNet to analyze text semantical structure is supplied with the capability to perform fine-grained entity typing of terms appear in the given text that are available in DBPedia similar to Wikification (e.g. SpotLight project http://demo.dbpedia-spotlight.org/).


# How to use it ?

The usage details described in SemCluster paper (to appear soon).


# What is the alignment syntax ?

Each line in the file represents one-to-one mapping from a DBPedia ontological class to its exact or semantically equivalent synset in WordNet. Each line is formatted in the following syntax:

        dbp:Class_Name , wn:SynSet_Offset , Depth

# Notes:

1) dbp:Class_Name is a DBPedia class e.g. http://dbpedia.org/ontology/Agent, http://dbpedia.org/ontology/MusicalArtist, ... etc.

2) WordNet index.noun and data.noun have been sorted and reindexed for faster on-disk-access, hence wn:SynSet_Offset may not indicate the original byte offset of certain synset.

3) Depth is an integer number specifies the depth of a given class in DBPedia schema owl file, e.g. the depth of http://dbpedia.org/ontology/Agent is 1, the depth of http://dbpedia.org/ontology/MusicalArtist is 4.


Depth value is virtual for computational convenience, such that, each depth value must be added one (depth+1) because we chose to ignore the root (http://www.w3.org/2002/07/owl#Thing).
