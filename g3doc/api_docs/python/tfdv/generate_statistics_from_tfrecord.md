<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tfdv.generate_statistics_from_tfrecord" />
<meta itemprop="path" content="Stable" />
</div>

# tfdv.generate_statistics_from_tfrecord

``` python
tfdv.generate_statistics_from_tfrecord(
    data_location,
    output_path=None,
    stats_options=options.StatsOptions(),
    pipeline_options=None
)
```

Compute data statistics from TFRecord files containing TFExamples.

Runs a Beam pipeline to compute the data statistics and return the result
data statistics proto.

This is a convenience method for users with data in TFRecord format.
Users with data in unsupported file/data formats, or users who wish
to create their own Beam pipelines need to use the 'GenerateStatistics'
PTransform API directly instead.

#### Args:

* <b>`data_location`</b>: The location of the input data files.
* <b>`output_path`</b>: The file path to output data statistics result to. If None, we
    use a temporary directory. It will be a TFRecord file containing a single
    data statistics proto, and can be read with the 'load_statistics' API.
* <b>`stats_options`</b>: Options for generating data statistics.
* <b>`pipeline_options`</b>: Optional beam pipeline options. This allows users to
    specify various beam pipeline execution parameters like pipeline runner
    (DirectRunner or DataflowRunner), cloud dataflow service project id, etc.
    See https://cloud.google.com/dataflow/pipelines/specifying-exec-params for
    more details.


#### Returns:

A DatasetFeatureStatisticsList proto.