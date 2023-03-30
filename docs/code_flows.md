# Code Flows

```mermaid
  graph TD;
      A-->B;
      A-->C;
      B-->D;
      C-->D;
```

```mermaid
stateDiagram-v2;
    [*] --> meta_render;
    meta_render --> render_what;
    meta_render --> duration;
    duration --> augment_unique_collection_since;
    duration --> augment_weighed_duration_since;
    meta_render --> augment_augment_unique_collection;
    augment_augment_unique_collection --> augment_augment_unique_collection_er;
    augment_augment_unique_collection --> augment_augment_unique_collection_ck;
    augment_augment_unique_collection_ck --> augment_weighed_cumulative_state;
    augment_weighed_cumulative_state --> augment_weighed_cumulative_slice;
    augment_weighed_cumulative_slice --> augment_weighed_slice;
    meta_render --> [*];
```

[See file](https://bdekoz.github.io/alpha60-docs/html.doxygen.20230329/a60-svg-collection-augment_8h.html)
