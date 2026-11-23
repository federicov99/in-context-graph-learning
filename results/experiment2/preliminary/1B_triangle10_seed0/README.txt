Results of graph_icl_explorer.ipynb: meta-llama/Llama-3.2-1B, triangular graph with 100 words,
32 random walks of 20000 tokens, block 13 of 16, window 300 tokens, seed 0.

accuracy_mean.csv     context = number of words seen; mean_accuracy = probability on the valid next words,
                      averaged over walks; standard_error; belief_fit and two_line_fit = the fitted curves.
accuracy_binned.csv   the log-binned points that were fitted (and plotted).
fit_parameters.csv    belief-curve parameters p0, q, b, gamma, alpha, N* with 68% bootstrap intervals.
bootstrap_fits.csv    one row per bootstrap refit (walks resampled with replacement).
representations.csv   per stored context length: words seen in the window, normalized Dirichlet energy and
                      its random-placement baseline (mean, std of 20 shuffles), PCA R² and its baseline.
pca_coordinates.csv   per stored context length and word: PC1, PC2, and the coordinates lined up with the
                      true drawing (aligned_x, aligned_y; centred, unit total size).
graph_nodes.csv       node number, word, token id, number of neighbours, position in the drawing.
graph_edges.csv       one row per edge.
data.npz              numpy.load("data.npz"): accuracy [walk, position] (position k = after k+1 words),
                      walks [walk, position] (node numbers), context_points, adjacency, layout, words,
                      word_tokens, pca_coordinates and pca_aligned [context point, node, 2] (NaN = not seen),
                      word_counts [context point, node] = occurrences in the window over all walks,
                      word_means [context point, node, hidden size] (float16; only if small enough).
summary.json          settings and main results.
