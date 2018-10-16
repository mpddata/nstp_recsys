
## 1  cd into wals_ml_engine folder

## 2 define bucket location

export IN_BUCKET=gs://mpd-recsys/nst/bq_data/nst_recsys_output_bq.csv



## 3 start training - local at instance and save the recommendations result to GCP bucket ( can be configure at mltrain.sh)
./mltrain.sh local  ${IN_BUCKET} --data-type web_views --use-optimized --output-dir trainer

