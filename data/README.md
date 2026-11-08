# 未来数据字段设计

当前目录不包含路线或文化点记录。只有在字段对应的信息经过适当来源核验后，才应录入实际数据；不得用示例或猜测值填充尚未确认的事实。

## 路线（Route）

建议字段：

- `id`：稳定的内部标识。
- `name`、`official_name`：常用名称与官方名称，分别记录并注明来源。
- `destination`：国家、地区及必要的行政区层级。
- `operator`：路线管理或运营机构。
- `distance_km`、`estimated_duration`、`difficulty`、`elevation_gain_m`：路线量化属性及定义口径。
- `start_points`、`end_points`、`segments`：起终点与分段；地理坐标仅在核验后记录。
- `themes`：文化、自然或其他主题及其分类依据。
- `accessibility`、`transport`、`facilities`：无障碍、交通与设施信息，注明适用范围及易变性。
- `status`、`valid_from`、`valid_until`：状态及有效时间；易变状态须有更新时间。
- `sources`：来源记录数组，包含发布者、标题、URL 或标识、发布日期/访问日期、支持的字段及证据等级。
- `verification_status`、`verified_at`、`review_notes`：核验状态、核验时间和限制说明。

## 文化点（CulturalPoint）

建议字段：

- `id`：稳定的内部标识。
- `name`、`alternate_names`：名称与异名，并保留语言或拼写信息。
- `point_type`：地点、建筑、遗产、机构、实践等受控类别。
- `location`：地址或坐标；需记录精度、来源和核验状态，不从用户位置推断。
- `description`：经来源支持的简明介绍。
- `claims`：可独立核验的主张数组，每项包含内容、类型（事实/解释/推测）、适用时间范围和来源关联。
- `cultural_context`：语境说明及相关社群自我表述，避免无依据的概括。
- `route_ids`：关联路线标识。
- `sources`、`verification_status`、`verified_at`、`review_notes`：来源、核验状态、核验时间和限制，字段含义与路线数据一致。

## 数据约定

- 路线状态、交通、开放时间等易变字段必须带时间信息，并设置复核流程。
- 来源应细化到支持具体字段或主张的材料，不以单一泛化链接为整条记录背书。
- 未核验的字段应保持空缺或显式标记为待核验；不得以默认值伪装成已知信息。
- 坐标与地址采用明确的坐标参考系和粒度说明；无法确认时不录入。
