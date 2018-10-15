
## define bucket location

export IN_BUCKET=gs://recserve_mp-bigdata/nst/nst.csv

-- [Optional]  export OUT_BUCKET=gs://recserve_mp-bigdata/nst


## copy GA training data from google cloud bucket to GCE instance 
gsutil  cp -r gs://recserve_mp-bigdata/nst/nst.csv  data


## start training - local at instance and save the result to bucket
./mltrain.sh local  ${IN_BUCKET} --data-type web_views --use-optimized --output-dir ${OUT_BUCKET}

