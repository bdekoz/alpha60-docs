# meta_render

[source a60-cache-recache-synthesize-uniques.cc](https://bdekoz.github.io/alpha60-docs/html.doxygen.20230329/a60-cache-recache-synthesize-uniques_8cc.html)

[source a60-svg-collection-augment.h](https://bdekoz.github.io/alpha60-docs/html.doxygen.20230329/a60-svg-collection-augment_8h.html)

@mermaid{metarender}

```{mermaid}
stateDiagram-v2
    [*] --> meta_render
    meta_render --> render_reconsider_local
    state if_state<<choice>>

    render_reconsider_local --> if_state
    if_state --> augment_unique_collection : cumulative
    augment_unique_collection --> augment_unique_collection_er
    augment_unique_collection --> augment_unique_collection_ck
    augment_unique_collection_ck --> augment_weighed_cumulative_state
    augment_weighed_cumulative_state --> augment_weighed_cumulative_slice
    augment_weighed_cumulative_slice --> augment_weighed_slice
    augment_weighed_slice --> augment_weighed_swarm_once : oncep
    augment_weighed_slice --> augment_weighed_swarm_variations : variationsp
    augment_weighed_slice --> augment_weighed_swarm_vcarto_composite

    if_state --> augment_weighed_duration_since: week
    if_state --> augment_weighed_duration_since: day
    if_state --> augment_weighed_duration_since: hour
    augment_weighed_duration_since --> duration_since_each
    duration_since_each --> augment_swarm_duration
    augment_swarm_duration --> augment_weighed_swarm_vcarto_composite
    augment_weighed_swarm_vcarto_composite --> [*]
```
