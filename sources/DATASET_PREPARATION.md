# Waymo Dataset Preparation

**Step 1:** Download Waymo Open Motion Dataset (we use the `scenario protocol` form dataset), and organize the data as follows: 
```
ScenarioDescription
├── SceneInformation
├── EgoVehicleInformation
├── OtherVehiclesInformation
├── SemanticInfrastructure
│   ├── near_junction
│   │   ├── off_ramp_exit
│   ├── ...
├── ExtroSpectivePredictionFeatures
│   ├── tv_dist_to_ev
│   ├── tv_speed_to_ev
│   ├── tv_ttc_to_ev
│   ├── ego_dist_to_tv
│   ├── ego_speed_to_tv
│   ├── ego_ttc_to_tv
│   ├── ego_dist_to_ev
│   ├── ego_speed_to_ev
│   ├── ego_ttc_to_ev
│   ├── ...
├── ...

```
**Step 2:** Install the [Waymo Open Dataset API](https://github.com/waymo-research/waymo-open-dataset/blob/master/docs/quick_start.md) as follows: 
```
pip install waymo-open-dataset-tf-2-6-0
```
```
# MTR Data input format
Dataset
├── Sample_1
│   ├── track_infos
│   │   ├── object_id (agent_nr*1)
│   │   ├── object_types (agent_nr*1)
│   │   ├── trajs (agent_nr, 91, 10) # agent_nr can be 64 or 19
│   ├── dynamic_map_infos
│   │   ├── lane_id (len 91)
│   │   ├── state (len 91)
│   │   ├── stop_point (len 91)
│   ├── map_infos
│   │   ├── lane (len 212)
│   │   │   ├── 'id': 139
│   │   │   ├── 'speed_limit_mph': 10.0
│   │   │   ├── 'type': 'TYPE_SURFACE_STREET'
│   │   │   ├── 'interpolating': False
│   │   │   ├── 'entry_lanes': []
│   │   │   ├── 'exit_lanes': []
│   │   │   ├── 'left_boundary' (len 3)
│   │   │   │   ├── 'start_index': 0, 
│   │   │   │   ├── 'end_index': 5, 
│   │   │   │   ├── 'feature_id': 5, 
│   │   │   │   ├── 'boundary_type': 0
│   │   │   ├── 'right_boundary' (len 2)
│   │   │   │   ├── 'start_index': 1
│   │   │   │   ├── 'end_index': 13
│   │   │   │   ├── 'feature_id': 5
│   │   │   │   ├── 'boundary_type': 'TYPE_UNKNOWN'
│   │   │   ├── 'polyline_index': (12222, 12270)
│   │   ├── road_line (len 91)
│   │   ├── road_edge (len 91)
│   │   ├── stop_sign (len 91)
│   │   ├── crosswalk (len 91)
│   │   ├── speed_bump (len 91)
│   │   ├── all_polylines (len 91)
│   ├── scenario_id
│   ├── timestamps_seconds (1 + 90 timestamps)
│   │   ├── current_time_index
│   │   ├── sdc_track_index
│   ├── dynamic_map_infos
├── Sample_2
├── ...
```

