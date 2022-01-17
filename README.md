# IMoJIE_with_GRU-decoder
Based on the IMoJIE-Model [arXiv:2005.08178v1] [https://github.com/dair-iitd/imojie] I tried to replace its LSTM-decoder with a GRU-Decoder for a possible speedup. My results reveal no increase in speed with the GRU-decoder. However, it turns out that the function _gather_final_log_probs in copy_seq2seq_bahdanu.py takes 97,63 % of the time per decoder-step indicating that this function needs to be heavily optimized. It's further work for me to do so as the IMoJIE model is criticized for a very slow extraction time [arXiv:2010.03147v1].

I wrote a research paper documentating the experiments and plan to publish it after completing the research.   
