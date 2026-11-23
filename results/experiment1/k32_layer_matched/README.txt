Results of the graph-walk head-ablation notebook: meta-llama/Llama-3.1-8B, square 4×4, 16 words, 16 walks.

accuracy.csv             mean valid-neighbour probability (0-1) at every scored context length, one column per
                         condition (unsmoothed).
effects-summary.csv      per head group, head count k and scope: mean valid-neighbour probability over words
                         701-1400, its drop relative to the intact model on the same walks
                         with a 95% paired bootstrap interval over walks and, where a matching control exists, the
                         control's drop and the drop beyond the control with its interval. Rows: ablated groups,
                         layer-matched controls, then random controls. "random" has as many heads as the largest
                         single-family group, "random_union" as many as the largest union; for these rows k is the
                         number of random heads and matched_k the largest head count.
crossover-summary.csv    per k: (previous-token drop in the history - at the final word) minus (the same for
                         induction heads), with a 95% bootstrap interval over walks.
effects-table.png        both tables as one image, coloured by the size of each drop.
aggregated-results.npz   numpy.load(...): accuracy [condition, position], accuracy_by_walk [condition, walk, position],
                         positions, condition_names, pca [condition, cutoff, word, 2] (NaN = word not yet seen),
                         variance_fraction, graph_overlap [condition, cutoff], cutoffs, window_size,
                         node_count [cutoff, word], walks, edges, graph_coordinates, words.
node-map.csv             the word of every vertex and its position in the reference drawing.
results-schema.json      the list of conditions and a description of every array.
experiment.json          model revision, graph, words and token ids, head rankings and groups, seeds and settings.
execution-settings.json  GPU and chunk sizes of each session that contributed to the run.
native-check.json        differences between the engine and ordinary Hugging Face forward passes.
*.png, *.pdf             the figures.
