Results of graph_icl_explorer.ipynb: meta-llama/Llama-3.1-8B, hexagonal graph with 30 words,
32 random walks of 8000 tokens, block 26 of 32, window 90 tokens, seed 0.

accuracy_mean.csv     context = number of words seen; mean_accuracy = probability on the valid next words,
                      averaged over walks; standard_error; belief_fit and two_line_fit = the fitted curves
                      (the two-line fit's onset t_c is in summary.json); mean_revealed_share = share of the
                      current word's neighbours already seen right after it in the walk (lookup reference).
accuracy_binned.csv   the log-binned points that were fitted (and plotted), with the same columns.
fit_parameters.csv    belief-curve parameters p0, q, b, gamma, alpha, N* with 68% bootstrap intervals.
bootstrap_fits.csv    one row per bootstrap refit (walks resampled with replacement).
per_walk_fits.csv     one row per walk: belief-curve fit of that walk alone, transition width (decades between 25%
                      and 75% of the rise), N* from the odd and from the even positions, BIC and held-out error
                      of the belief curve and of the two lines.
single_walk_calibration.csv  the three single-walk diagnostics for the real walks and for the two simulations
                      (smooth walks, sharp jumps), and which simulation the real walks are closer to.
representations.csv   per stored context length: words seen in the window, normalized Dirichlet energy and
                      its random-placement baseline (mean, std of 20 shuffles), PCA R² and its baseline.
pca_coordinates.csv   per stored context length and word: PC1, PC2, and the coordinates lined up with the
                      true drawing (aligned_x, aligned_y; centred, unit total size).
graph_nodes.csv       node number, word, token id, number of neighbours, position in the drawing.
graph_edges.csv       one row per edge.
data.npz              numpy.load("data.npz"): accuracy and revealed_share [walk, position] (position k = after
                      k+1 words), walks [walk, position] (node numbers), context_points, adjacency, layout, words,
                      word_tokens, pca_coordinates and pca_aligned [context point, node, 2] (NaN = not seen),
                      word_counts [context point, node] = occurrences in the window over all walks,
                      word_means [context point, node, hidden size] (float16; only if small enough).
summary.json          settings and main results.
