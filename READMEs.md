Based on the IMoJIE-Model [arXiv:2005.08178v1] [https://github.com/dair-iitd/imojie] I tried to replace its LSTM-decoder with a GRU-decoder for a possible speedup in time.
My results hereby reveal no significant increase in speed with the GRU-decoder. However, it turns out that the function _gather_final_log_probs in copy_seq2seq_bahdanu.py takes
97,63 % of the time per decoder-step indicating that this function needs to be heavily optimized.It will be further work for me to do so as 
the IMoJIE model is criticized for a very slow extraction time [arXiv:2010.03147v1, OPEN-IE6 model].

I wrote a research-paper-like 'Belegarbeit' in german documenting the experiments which I release and plan to extend. Further topics will herein be:

• The optimization of the function CopyNetSeq2Seq._gather_final_log_probs.

• The training with bigger BERT encoders to analyse the performance gain as IMoJIE encodes the entire Input consisting of the input sentence 
  and all extractions so far for every iteration. With it I want to proof that the excecution time won't increase any further with larger BERT encoders 
  and yield a significant performence boost.
