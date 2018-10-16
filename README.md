
## define bucket location

export IN_BUCKET=gs://mpd-recsys/nst/bq_data/nst_recsys_output_bq.csv

-- [Optional]  export OUT_BUCKET=gs://mpd-recsys/nst/model/model_output.csv


## copy GA training data from google cloud bucket to GCE instance 
gsutil  cp -r gs://mpd-recsys/nst/bq_data/nst_recsys_output_bq.csv data


## start training - local at instance and save the result to bucket
./mltrain.sh local  ${IN_BUCKET} --data-type web_views --use-optimized --output-dir ${OUT_BUCKET}

