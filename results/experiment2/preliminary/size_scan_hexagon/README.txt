Size scan of graph_icl_explorer.ipynb: meta-llama/Llama-3.1-8B, hexagonal graphs, sizes [4, 5, 7, 8, 10, 11, 12], word seeds [0, 1, 2, 3, 4], 32 walks per run, SEED 0.
scan_parameters.csv      one row per size and word seed: belief-curve parameters p0, q, b, gamma,
                         alpha, N*, the two-line onset t_c, each with 68% bootstrap intervals over walks;
                         whether the fit is reliable (and why not); the revealed share's N* and t_c
                         (lookup reference) and N*_model_over_lookup. seed = SEED + 1000 x GRAPH_SIZE
                         + word seed, the random seed of that run's words and walks.
scan_accuracy_binned.csv the log-binned mean accuracy of each run with both fitted curves.
scan_data.npz            for each run (key suffix <N>_words_seed<s>): accuracy_..., revealed_share_...
                         [walk, position] (position k = after k + 1 words) and walks_... [walk, position].
