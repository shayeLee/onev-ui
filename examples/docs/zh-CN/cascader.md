## Cascader 级联选择器

当一个数据集合有清晰的层级结构时，可通过级联选择器逐级查看并选择。

### 基本用法

:::demo

```html

<div class="block">
    <span class="demonstration">单选</span>
    <el-cascader
            v-model="val1"
            :options="list"
            :props="props1"
            clearable></el-cascader>
</div>
<div class="block">
    <span class="demonstration">多选</span>
    <el-cascader
            :options="options"
            :props="props"
            collapse-tags
            clearable></el-cascader>
</div>

<script>
    export default {
        data() {
            return {
                props1: {
                    lazy: true,
                    lazyLoad: (node, resolve) => {
                        let nodes = [];
                        const { level, data } = node;
                        
                        setTimeout(() => {
                            resolve({
                                module: [
                                    {
                                        "label": "account",
                                        "value": "account",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "ad",
                                        "value": "ad",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "application",
                                        "value": "application",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "au",
                                        "value": "au",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "backup",
                                        "value": "backup",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "battle",
                                        "value": "battle",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "clean",
                                        "value": "clean",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "cloudRedis",
                                        "value": "cloudRedis",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "cloudredis",
                                        "value": "cloudredis",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "comment",
                                        "value": "comment",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "common",
                                        "value": "common",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "community",
                                        "value": "community",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "core",
                                        "value": "core",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "dataCenterMysqlMaster",
                                        "value": "dataCenterMysqlMaster",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "dataCenterMysqlSlave",
                                        "value": "dataCenterMysqlSlave",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "dataNode",
                                        "value": "dataNode",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "dbtest",
                                        "value": "dbtest",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "druid",
                                        "value": "druid",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "elk",
                                        "value": "elk",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "es",
                                        "value": "es",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "flume",
                                        "value": "flume",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "game",
                                        "value": "game",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "gameTest",
                                        "value": "gameTest",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "gameVersion",
                                        "value": "gameVersion",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "gametest",
                                        "value": "gametest",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "gateway",
                                        "value": "gateway",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "global",
                                        "value": "global",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "gm",
                                        "value": "gm",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "gs",
                                        "value": "gs",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "h5active",
                                        "value": "h5active",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "haproxy",
                                        "value": "haproxy",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "idleModule",
                                        "value": "idleModule",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "im_service",
                                        "value": "im_service",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "infinity",
                                        "value": "infinity",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "kafka",
                                        "value": "kafka",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "kbsCore",
                                        "value": "kbsCore",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "keep",
                                        "value": "keep",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "kite_watch",
                                        "value": "kite_watch",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "kudu",
                                        "value": "kudu",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "link",
                                        "value": "link",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "localRedisSlave",
                                        "value": "localRedisSlave",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "log",
                                        "value": "log",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "logMysqlMaster",
                                        "value": "logMysqlMaster",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "logMysqlSlave",
                                        "value": "logMysqlSlave",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "loget",
                                        "value": "loget",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "logic",
                                        "value": "logic",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "login",
                                        "value": "login",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "map",
                                        "value": "map",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "match",
                                        "value": "match",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "mongoCluster",
                                        "value": "mongoCluster",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "monitor",
                                        "value": "monitor",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "msyqlMaster",
                                        "value": "msyqlMaster",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "msyqlSlave",
                                        "value": "msyqlSlave",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "mysql",
                                        "value": "mysql",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "mysqlBackup",
                                        "value": "mysqlBackup",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "mysqlMaster",
                                        "value": "mysqlMaster",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "mysqlSingle",
                                        "value": "mysqlSingle",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "mysqlSlave",
                                        "value": "mysqlSlave",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "nameNode",
                                        "value": "nameNode",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "onemtDeliver",
                                        "value": "onemtDeliver",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "onemtService",
                                        "value": "onemtService",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "opsNetwork",
                                        "value": "opsNetwork",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "opsPlatform",
                                        "value": "opsPlatform",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "pingService",
                                        "value": "pingService",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "platform",
                                        "value": "platform",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "poc",
                                        "value": "poc",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "proxy",
                                        "value": "proxy",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "push",
                                        "value": "push",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "queue",
                                        "value": "queue",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "rabbitmq",
                                        "value": "rabbitmq",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "rebuild",
                                        "value": "rebuild",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "recharge",
                                        "value": "recharge",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "redis",
                                        "value": "redis",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "redisMaster",
                                        "value": "redisMaster",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "redisSlave",
                                        "value": "redisSlave",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "redis_master",
                                        "value": "redis_master",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "review",
                                        "value": "review",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "review_server",
                                        "value": "review_server",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "security",
                                        "value": "security",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "sentry",
                                        "value": "sentry",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "test",
                                        "value": "test",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "translate",
                                        "value": "translate",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "uap",
                                        "value": "uap",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "usercenter",
                                        "value": "usercenter",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "web",
                                        "value": "web",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "world",
                                        "value": "world",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "worldDbSlave",
                                        "value": "worldDbSlave",
                                        "leaf": true,
                                        "level": 1
                                    }
                                ],
                                project: [
                                    {
                                        "label": "bigData",
                                        "value": "bigData",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "boe",
                                        "value": "boe",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "dk",
                                        "value": "dk",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "dm",
                                        "value": "dm",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "emc",
                                        "value": "emc",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "gameSupport",
                                        "value": "gameSupport",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "gos",
                                        "value": "gos",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "gs",
                                        "value": "gs",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "koh",
                                        "value": "koh",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "koh2",
                                        "value": "koh2",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "koh_velia",
                                        "value": "koh_velia",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "kow",
                                        "value": "kow",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "kow_ea",
                                        "value": "kow_ea",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "kow_eu",
                                        "value": "kow_eu",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "kow_sea",
                                        "value": "kow_sea",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "ld",
                                        "value": "ld",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "lob",
                                        "value": "lob",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "mcw",
                                        "value": "mcw",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "mcw_eu",
                                        "value": "mcw_eu",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "mcw_us",
                                        "value": "mcw_us",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "md",
                                        "value": "md",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "mk",
                                        "value": "mk",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "oe",
                                        "value": "oe",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "opsSupport",
                                        "value": "opsSupport",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "pos",
                                        "value": "pos",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "pp",
                                        "value": "pp",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "resourcePool",
                                        "value": "resourcePool",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "rok",
                                        "value": "rok",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "roks",
                                        "value": "roks",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "ros",
                                        "value": "ros",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "sdkSupport",
                                        "value": "sdkSupport",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "sf",
                                        "value": "sf",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "sh",
                                        "value": "sh",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "sh_en",
                                        "value": "sh_en",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "sh_kr",
                                        "value": "sh_kr",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "sh_tw",
                                        "value": "sh_tw",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "sh_us",
                                        "value": "sh_us",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "woe",
                                        "value": "woe",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "woe_cn",
                                        "value": "woe_cn",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "ww",
                                        "value": "ww",
                                        "leaf": true,
                                        "level": 1
                                    }
                                ],
                                set: [
                                    {
                                        "label": "dev",
                                        "value": "dev",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "idleSet",
                                        "value": "idleSet",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "migration",
                                        "value": "migration",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "prod",
                                        "value": "prod",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "review",
                                        "value": "review",
                                        "leaf": true,
                                        "level": 1
                                    },
                                    {
                                        "label": "test",
                                        "value": "test",
                                        "leaf": true,
                                        "level": 1
                                    }
                                ]
                            }[node.value]);
                        }, 300);
                    },
                },
                props: {multiple: true},
                val1: [],
                options: [
                  {
                    value: 1,
                    label: '东南',
                    children: [{
                        value: 2,
                        label: '上海',
                        children: [
                            {value: 3, label: '普陀'},
                            {value: 4, label: '黄埔'},
                            {value: 5, label: '徐汇'}
                        ]
                    }, {
                        value: 7,
                        label: '江苏',
                        children: [
                            {value: 8, label: '南京'},
                            {value: 9, label: '苏州'},
                            {value: 10, label: '无锡'}
                        ]
                    }, {
                        value: 12,
                        label: '浙江',
                        children: [
                            {value: 13, label: '杭州'},
                            {value: 14, label: '宁波'},
                            {value: 15, label: '嘉兴'}
                        ]
                    }]
                }, {
                    value: 17,
                    label: '西北',
                    children: [{
                        value: 2,
                        label: '陕西',
                        children: [
                            {value: 19, label: '西安'},
                            {value: 20, label: '延安'}
                        ]
                    }, {
                        value: 7,
                        label: '新疆维吾尔族自治区',
                        children: [
                            {value: 22, label: '乌鲁木齐'},
                            {value: 23, label: '克拉玛依'}
                        ]
                    }]
                }, {
                    value: 27,
                    label: '西南',
                    children: [{
                        value: 28,
                        label: '四川',
                        children: [
                            {value: 29, label: '成都'},
                            {value: 30, label: '乐山'}
                        ]
                    }, {
                        value: 31,
                        label: '重庆',
                        children: [
                            {value: 32, label: '渝中'},
                            {value: 33, label: '万州'},
                            {value: 34, label: '江北'},
                        ]
                    }]
                }],
                list: [
                    {
                        "label": "module",
                        "value":"module",
                        "children":[],
                        "level":0
                    },
                    {
                        "label": "project",
                        "value": "project",
                        "children": [],
                        "level": 0
                    },
                    {
                        "label": "set",
                        "value": "set",
                        "children": [],
                        "level": 0
                    }
                ]
            };
        },
    };
</script>
```

:::

### GM王国控件

:::demo

```html

<div class="block">
    <el-cascader
            :options="options"
            :props="props"
            select-type="king"
            collapse-tags
            clearable></el-cascader>
</div>

<script>
    export default {
        data() {
            return {
                props: {multiple: true},
                val1: [],
                options: [{
                    "value": 1,
                    "label": "美洲区",
                    "children": [{"value": 10001, "label": "王国10001"}, {
                        "value": 10002,
                        "label": "王国10002 (已合服)：10003-10011"
                    }, {"value": 10012, "label": "王国10012"}]
                }, {
                    "value": 2,
                    "label": "欧洲区",
                    "children": [{"value": 20001, "label": "王国20001 (已合服)：20002-20200"}, {
                        "value": 20201,
                        "label": "王国20201"
                    }, {"value": 20202, "label": "王国20202"}, {"value": 20203, "label": "王国20203"}, {
                        "value": 20204,
                        "label": "王国20204"
                    }, {"value": 20205, "label": "王国20205"}, {"value": 20206, "label": "王国20206"}, {
                        "value": 20207,
                        "label": "王国20207"
                    }, {"value": 20208, "label": "王国20208"}]
                }]
            };
        }
    };
</script>
```

:::

### 置顶已选

:::demo

```html


<div class="block">
    <el-cascader
            :props="props"
            :options="options"
            clearable
    ></el-cascader>
</div>

<script>
    export default {
        data() {
            return {
                props: {multiple: true},
                options: [
                    {
                        "value": 2,
                        "label": "充值活动[2]",
                        "children": [
                            {
                                "value": 103,
                                "label": "累天充值[103]",
                                "children": [
                                    {
                                        "value": 2103008,
                                        "label": "累天充值-2天[2103008]"
                                    },
                                    {
                                        "value": 2103009,
                                        "label": "累天充值-3天[2103009]"
                                    },
                                    {
                                        "value": 2103010,
                                        "label": "累天充值-4天[2103010]"
                                    }
                                ]
                            },
                            {
                                "value": 101,
                                "label": "每日充值[101]",
                                "children": [
                                    {
                                        "value": 2101008,
                                        "label": "新版带小活动每日充值[2101008]"
                                    },
                                    {
                                        "value": 2101009,
                                        "label": "新版不带小活动每日充值[2101009]"
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "value": 5,
                        "label": "限时活动（限时任务）[5]",
                        "children": [
                            {
                                "value": 27,
                                "label": "累计签到天数[27]",
                                "children": [
                                    {
                                        "value": 5027002,
                                        "label": "限时福利-登录奖励1天[5027002]"
                                    },
                                    {
                                        "value": 5027003,
                                        "label": "限时福利-登录奖励2天[5027003]"
                                    },
                                    {
                                        "value": 5027004,
                                        "label": "限时福利-登录奖励3天[5027004]"
                                    },
                                    {
                                        "value": 5027005,
                                        "label": "限时福利-登录奖励4天[5027005]"
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "value": 6,
                        "label": "特殊英雄兑换活动[6]",
                        "children": [
                            {
                                "value": 1,
                                "label": "亚瑟王传说[1]",
                                "children": [
                                    {
                                        "value": 6001001,
                                        "label": "亚瑟王传说（不延迟）[6001001]"
                                    },
                                    {
                                        "value": 6001002,
                                        "label": "亚瑟王传说（延迟一天）-前三周[6001002]"
                                    }
                                ]
                            },
                            {
                                "value": 2,
                                "label": "史诗英雄[2]",
                                "children": [
                                    {
                                        "value": 6002001,
                                        "label": "四大史诗兑换[6002001]"
                                    }
                                ]
                            },
                            {
                                "value": 4,
                                "label": "著名学者[4]",
                                "children": [
                                    {
                                        "value": 6004001,
                                        "label": "著名学者（不延迟）[6004001]"
                                    },
                                    {
                                        "value": 6004002,
                                        "label": "著名学者（延迟一天）-前三周[6004002]"
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "value": 7,
                        "label": "使用道具活动[7]",
                        "children": [
                            {
                                "value": 1,
                                "label": "湖边钓鱼[1]",
                                "children": [
                                    {
                                        "value": 7001001,
                                        "label": "钓鱼（技能点）[7001001]"
                                    }
                                ]
                            },
                            {
                                "value": 2,
                                "label": "烘焙大赛[2]",
                                "children": [
                                    {
                                        "value": 7002001,
                                        "label": "烘培（粮草）[7002001]"
                                    }
                                ]
                            },
                            {
                                "value": 3,
                                "label": "镇压叛军[3]",
                                "children": [
                                    {
                                        "value": 7003001,
                                        "label": "平叛（联盟财富）[7003001]"
                                    }
                                ]
                            },
                            {
                                "value": 4,
                                "label": "挖宝[4]",
                                "children": [
                                    {
                                        "value": 7004001,
                                        "label": "挖宝（银币）[7004001]"
                                    }
                                ]
                            },
                            {
                                "value": 5,
                                "label": "募兵[5]",
                                "children": [
                                    {
                                        "value": 7005001,
                                        "label": "募兵（士兵）[7005001]"
                                    }
                                ]
                            },
                            {
                                "value": 6,
                                "label": "炼金[6]",
                                "children": [
                                    {
                                        "value": 7006001,
                                        "label": "炼金（资质经验）[7006001]"
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "value": 8,
                        "label": "个人冲榜[8]",
                        "children": [
                            {
                                "value": 100,
                                "label": "亲密度提升[100]",
                                "children": [
                                    {
                                        "value": 8100002,
                                        "label": "个人亲密-过渡[8100002]"
                                    },
                                    {
                                        "value": 8100003,
                                        "label": "个人亲密-过渡带区服亲密门票[8100003]"
                                    },
                                    {
                                        "value": 8100004,
                                        "label": "个人亲密[8100004]"
                                    },
                                    {
                                        "value": 8100005,
                                        "label": "个人亲密-带区服亲密门票[8100005]"
                                    },
                                    {
                                        "value": 8100006,
                                        "label": "个人亲密-带多区亲密门票[8100006]"
                                    }
                                ]
                            },
                            {
                                "value": 102,
                                "label": "国力提升[102]",
                                "children": [
                                    {
                                        "value": 8102002,
                                        "label": "个人国力-过渡[8102002]"
                                    },
                                    {
                                        "value": 8102003,
                                        "label": "个人国力-过渡带区服国力门票（不带副榜耗银）[8102003]"
                                    },
                                    {
                                        "value": 8102004,
                                        "label": "个人国力[8102004]"
                                    },
                                    {
                                        "value": 8102005,
                                        "label": "个人国力-带区服国力门票[8102005]"
                                    },
                                    {
                                        "value": 8102006,
                                        "label": "个人国力-带多区国力门票[8102006]"
                                    }
                                ]
                            },
                            {
                                "value": 103,
                                "label": "资质提升[103]",
                                "children": [
                                    {
                                        "value": 8103002,
                                        "label": "个人资质-过渡[8103002]"
                                    },
                                    {
                                        "value": 8103003,
                                        "label": "个人资质-过渡带区服资质门票[8103003]"
                                    },
                                    {
                                        "value": 8103004,
                                        "label": "个人资质[8103004]"
                                    },
                                    {
                                        "value": 8103005,
                                        "label": "个人资质-带区服资质门票[8103005]"
                                    },
                                    {
                                        "value": 8103006,
                                        "label": "个人资质-带多区资质门票[8103006]"
                                    }
                                ]
                            },
                            {
                                "value": 104,
                                "label": "宴会人气值[104]",
                                "children": [
                                    {
                                        "value": 8104002,
                                        "label": "宴会冲榜-过渡[8104002]"
                                    },
                                    {
                                        "value": 8104003,
                                        "label": "宴会冲榜[8104003]"
                                    }
                                ]
                            },
                            {
                                "value": 106,
                                "label": "竞技场积分提升[106]",
                                "children": [
                                    {
                                        "value": 8106002,
                                        "label": "个人竞技场-过渡[8106002]"
                                    },
                                    {
                                        "value": 8106003,
                                        "label": "个人竞技场-过渡带区服竞技场门票[8106003]"
                                    },
                                    {
                                        "value": 8106004,
                                        "label": "个人竞技场[8106004]"
                                    },
                                    {
                                        "value": 8106005,
                                        "label": "个人竞技场-带区服竞技场门票[8106005]"
                                    },
                                    {
                                        "value": 8106006,
                                        "label": "个人竞技场-带多区竞技场门票[8106006]"
                                    }
                                ]
                            },
                            {
                                "value": 109,
                                "label": "关卡通关[109]",
                                "children": [
                                    {
                                        "value": 8109002,
                                        "label": "个人关卡-过渡[8109002]"
                                    },
                                    {
                                        "value": 8109003,
                                        "label": "个人关卡[8109003]"
                                    }
                                ]
                            },
                            {
                                "value": 117,
                                "label": "魅力值提升[117]",
                                "children": [
                                    {
                                        "value": 8117002,
                                        "label": "个人魅力-过渡[8117002]"
                                    },
                                    {
                                        "value": 8117003,
                                        "label": "个人魅力-过渡带区服魅力门票[8117003]"
                                    },
                                    {
                                        "value": 8117004,
                                        "label": "个人魅力[8117004]"
                                    },
                                    {
                                        "value": 8117005,
                                        "label": "个人魅力-带区服魅力门票[8117005]"
                                    },
                                    {
                                        "value": 8117006,
                                        "label": "个人魅力-带多区魅力门票[8117006]"
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "value": 9,
                        "label": "联盟冲榜[9]",
                        "children": [
                            {
                                "value": 200,
                                "label": "联盟国力提升[200]",
                                "children": [
                                    {
                                        "value": 9200002,
                                        "label": "联盟国力-过渡[9200002]"
                                    },
                                    {
                                        "value": 9200003,
                                        "label": "联盟国力[9200003]"
                                    },
                                    {
                                        "value": 9200004,
                                        "label": "联盟国力-带多区联盟势力门票[9200004]"
                                    }
                                ]
                            },
                            {
                                "value": 201,
                                "label": "联盟亲密度提升[201]",
                                "children": [
                                    {
                                        "value": 9201002,
                                        "label": "联盟亲密-过渡[9201002]"
                                    },
                                    {
                                        "value": 9201003,
                                        "label": "联盟亲密[9201003]"
                                    },
                                    {
                                        "value": 9201004,
                                        "label": "联盟亲密-带多区联盟亲密门票[9201004]"
                                    }
                                ]
                            },
                            {
                                "value": 202,
                                "label": "联盟竞技场积分提升[202]",
                                "children": [
                                    {
                                        "value": 9202002,
                                        "label": "联盟竞技场-过渡[9202002]"
                                    },
                                    {
                                        "value": 9202003,
                                        "label": "联盟竞技场[9202003]"
                                    },
                                    {
                                        "value": 9202004,
                                        "label": "联盟竞技场-带绝境战争门票[9202004]"
                                    }
                                ]
                            },
                            {
                                "value": 203,
                                "label": "联盟经验提升[203]",
                                "children": [
                                    {
                                        "value": 9203002,
                                        "label": "联盟经验-过渡[9203002]"
                                    },
                                    {
                                        "value": 9203003,
                                        "label": "联盟经验[9203003]"
                                    }
                                ]
                            },
                            {
                                "value": 206,
                                "label": "联盟资质提升[206]",
                                "children": [
                                    {
                                        "value": 9206002,
                                        "label": "联盟资质-过渡[9206002]"
                                    },
                                    {
                                        "value": 9206003,
                                        "label": "联盟资质[9206003]"
                                    },
                                    {
                                        "value": 9206004,
                                        "label": "联盟资质-带多区联盟资质门票[9206004]"
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "value": 12,
                        "label": "组队冲榜[12]",
                        "children": [
                            {
                                "value": 1,
                                "label": "战车大赛[1]",
                                "children": [
                                    {
                                        "value": 12001002,
                                        "label": "战车大赛-过渡[12001002]"
                                    },
                                    {
                                        "value": 12001003,
                                        "label": "战车大赛[12001003]"
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "value": 13,
                        "label": "个人+联盟冲榜[13]",
                        "children": [
                            {
                                "value": 1,
                                "label": "血腥夫人[1]",
                                "children": [
                                    {
                                        "value": 13001002,
                                        "label": "血腥夫人-过渡[13001002]"
                                    },
                                    {
                                        "value": 13001003,
                                        "label": "血腥夫人[13001003]"
                                    },
                                    {
                                        "value": 13001004,
                                        "label": "血腥夫人-过度带多区（含2区）血腥夫人门票[13001004]"
                                    },
                                    {
                                        "value": 13001005,
                                        "label": "血腥夫人-带多区（含2区）血腥夫人门票[13001005]"
                                    }
                                ]
                            },
                            {
                                "value": 2,
                                "label": "尼伯龙根的宝藏[2]",
                                "children": [
                                    {
                                        "value": 13002002,
                                        "label": "尼伯龙根宝藏-过渡[13002002]"
                                    },
                                    {
                                        "value": 13002003,
                                        "label": "尼伯龙根宝藏[13002003]"
                                    },
                                    {
                                        "value": 13002004,
                                        "label": "尼伯龙根宝藏-过度带多区（含2区）尼伯龙根宝藏门票[13002004]"
                                    },
                                    {
                                        "value": 13002005,
                                        "label": "尼伯龙根宝藏-带多区（含2区）尼伯龙根宝藏门票[13002005]"
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "value": 14,
                        "label": "个人小游戏[14]",
                        "children": [
                            {
                                "value": 1,
                                "label": "英雄之路[1]",
                                "children": [
                                    {
                                        "value": 14001002,
                                        "label": "英雄之路-过渡[14001002]"
                                    },
                                    {
                                        "value": 14001003,
                                        "label": "英雄之路[14001003]"
                                    }
                                ]
                            },
                            {
                                "value": 2,
                                "label": "沉船宝藏[2]",
                                "children": [
                                    {
                                        "value": 14002002,
                                        "label": "沉船宝藏-过渡[14002002]"
                                    },
                                    {
                                        "value": 14002003,
                                        "label": "沉船宝藏[14002003]"
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "value": 4,
                        "label": "直购礼包[4]",
                        "children": [
                            {
                                "value": 1,
                                "label": "现金礼包[1]",
                                "children": [
                                    {
                                        "value": 4001004,
                                        "label": "除了“个人势力-前3周”外所有势力榜礼包[4001004]"
                                    },
                                    {
                                        "value": 4001005,
                                        "label": "所有资质榜礼包[4001005]"
                                    },
                                    {
                                        "value": 4001006,
                                        "label": "所有竞技场榜礼包[4001006]"
                                    },
                                    {
                                        "value": 4001007,
                                        "label": "除了“个人亲密榜-前3周”所有亲密榜礼包[4001007]"
                                    },
                                    {
                                        "value": 4001008,
                                        "label": "除了“关卡榜-前3周”所有关卡榜礼包[4001008]"
                                    },
                                    {
                                        "value": 4001009,
                                        "label": "所有血腥夫人活动礼包[4001009]"
                                    },
                                    {
                                        "value": 4001010,
                                        "label": "所有尼伯龙根宝藏活动礼包[4001010]"
                                    },
                                    {
                                        "value": 4001011,
                                        "label": "除了“联盟经验榜-前3周”外所有联盟经验礼包[4001011]"
                                    },
                                    {
                                        "value": 4001012,
                                        "label": "所有宴会榜礼包[4001012]"
                                    },
                                    {
                                        "value": 4001015,
                                        "label": "新手情景礼包[4001015]"
                                    },
                                    {
                                        "value": 4001016,
                                        "label": "每日免费礼包[4001016]"
                                    },
                                    {
                                        "value": 4001017,
                                        "label": "个人亲密榜-前3周礼包[4001017]"
                                    },
                                    {
                                        "value": 4001018,
                                        "label": "周礼包（光环英雄）[4001018]"
                                    },
                                    {
                                        "value": 4001022,
                                        "label": "测试破冰礼包[4001022]"
                                    },
                                    {
                                        "value": 4001026,
                                        "label": "测试破冰礼包（4.13）[4001026]"
                                    },
                                    {
                                        "value": 4001027,
                                        "label": "资质周礼包（新）[4001027]"
                                    },
                                    {
                                        "value": 4001028,
                                        "label": "亲密周礼包（新）[4001028]"
                                    },
                                    {
                                        "value": 4001029,
                                        "label": "竞技场周礼包（新）[4001029]"
                                    },
                                    {
                                        "value": 4001030,
                                        "label": "国力出战周礼包（新）[4001030]"
                                    },
                                    {
                                        "value": 4001031,
                                        "label": "所有魅力榜礼包[4001031]"
                                    },
                                    {
                                        "value": 4001023,
                                        "label": "国力周礼包（旧）[4001023]"
                                    },
                                    {
                                        "value": 4001024,
                                        "label": "亲密周礼包（旧）[4001024]"
                                    },
                                    {
                                        "value": 4001025,
                                        "label": "资源周礼包（旧）[4001025]"
                                    }
                                ]
                            }
                        ]
                    }
                ]
            }
        }
    }
</script>
```

:::

### change事件

:::demo

```html

<div class="block">
    <el-cascader
            :options="options"
            @change="handleChange"
    ></el-cascader>
</div>

<script>
    export default {
        data() {
            return {
                options: [{
                    value: 'zhejiang',
                    label: 'Zhejiang',
                    children: [{
                        value: 'hangzhou',
                        label: 'Hangzhou',
                        children: [{
                            value: 'xihu',
                            label: 'West Lake'
                        }, {
                            value: 'binjiang',
                            label: 'Bin Jiang'
                        }]
                    }, {
                        value: 'ningbo',
                        label: 'NingBo',
                        children: [{
                            value: 'jiangbei',
                            label: 'Jiang Bei'
                        }, {
                            value: 'jiangdong',
                            label: 'Jiang Dong',
                            disabled: true
                        }]
                    }]
                }, {
                    value: 'jiangsu',
                    label: 'Jiangsu',
                    disabled: true,
                    children: [{
                        value: 'nanjing',
                        label: 'Nanjing',
                        children: [{
                            value: 'zhonghuamen',
                            label: 'Zhong Hua Men'
                        }]
                    }]
                }]
            };
        },
        methods: {
            handleChange(val) {
                console.log("cascader changed =>", val);
            }
        }
    };
</script>
```

:::

### Cascader Attributes

| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| value / v-model | 选中项绑定值 | - | — | — |
| options | 可选项数据源，键名可通过 `Props` 属性配置 | array | — | — |
| props | 配置选项，具体见下表 | object | — | — |
| size | 尺寸 | string | medium / small / mini | — |
| placeholder | 输入框占位文本 | string | — | 请选择 |
| disabled | 是否禁用 | boolean | — | false |
| clearable | 是否支持清空选项 | boolean | — | false |
| show-all-levels | 输入框中是否显示选中值的完整路径 | boolean | — | true |
| collapse-tags | 多选模式下是否折叠Tag | boolean | - | false |
| separator | 选项分隔符 | string | — | 斜杠' / ' |
| debounce | 搜索关键词输入的去抖延迟，毫秒 | number | — | 300 |
| before-filter | 筛选之前的钩子，参数为输入的值，若返回 false 或者返回 Promise 且被 reject，则停止筛选 | function(value) | — | — |
| popper-class | 自定义浮层类名   | string | —  | — |

### Cascader Events

| 事件名称      | 说明    | 回调参数      |
|---------- |-------- |---------- |
| change | 当选中节点变化时触发 | 选中节点的值 |
| expand-change | 当展开节点发生变化时触发 | 各父级选项值组成的数组 |
| blur | 当失去焦点时触发 | (event: Event) |
| focus | 当获得焦点时触发 | (event: Event) |
| visible-change | 下拉框出现/隐藏时触发 | 出现则为 true，隐藏则为 false |
| remove-tag | 在多选模式下，移除Tag时触发 | 移除的Tag对应的节点的值 |

### Cascader Methods

| 方法名 | 说明 | 参数 |
| ---- | ---- | ---- |
| getCheckedNodes | 获取选中的节点 | (leafOnly) 是否只是叶子节点，默认值为 `false` |

### Cascader Slots

| 名称     | 说明 |
|---------|-------------|
| - | 自定义备选项的节点内容，参数为 { node, data }，分别为当前节点的 Node 对象和数据 |
| empty  | 无匹配选项时的内容 |

### CascaderPanel Attributes

| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| value / v-model | 选中项绑定值 | - | — | — |
| options | 可选项数据源，键名可通过 `Props` 属性配置 | array | — | — |
| props | 配置选项，具体见下表 | object | — | — |

### CascaderPanel Events

| 事件名称      | 说明    | 回调参数      |
|---------- |-------- |---------- |
| change | 当选中节点变化时触发 | 选中节点的值 |
| expand-change | 当展开节点发生变化时触发 | 各父级选项值组成的数组 |

### CascaderPanel Methods

| 方法名 | 说明 | 参数 |
| ---- | ---- | ---- |
| getCheckedNodes | 获取选中的节点数组 | (leafOnly) 是否只是叶子节点，默认值为 `false` |
| clearCheckedNodes | 清空选中的节点 | - |

### CascaderPanel Slots

| 名称     | 说明 |
|---------|-------------|
| - | 自定义备选项的节点内容，参数为 { node, data }，分别为当前节点的 Node 对象和数据 |

### Props

| 参数     | 说明              | 类型   | 可选值 | 默认值 |
| -------- | ----------------- | ------ | ------ | ------ |
| expandTrigger | 次级菜单的展开方式 | string | click / hover | 'click' |
| multiple | 是否多选 | boolean | - | false |
| checkStrictly | 是否严格的遵守父子节点不互相关联 | boolean | - | false |
| emitPath | 在选中节点改变时，是否返回由该节点所在的各级菜单的值所组成的数组，若设置 false，则只返回该节点的值 | boolean | - | true |
| lazy | 是否动态加载子节点，需与 lazyLoad 方法结合使用 | boolean | - | false |
| lazyLoad | 加载动态数据的方法，仅在 lazy 为 true 时有效 | function(node, resolve)，`node`为当前点击的节点，`resolve`为数据加载完成的回调(必须调用) | - | - |
| value    | 指定选项的值为选项对象的某个属性值 | string | — | 'value' |
| label    | 指定选项标签为选项对象的某个属性值 | string | — | 'label' |
| children | 指定选项的子选项为选项对象的某个属性值 | string | — | 'children' |
| disabled | 指定选项的禁用为选项对象的某个属性值 | string | — | 'disabled' |
| leaf     | 指定选项的叶子节点的标志位为选项对象的某个属性值 | string | — | 'leaf' |
| checkSingleLastParent     | 倒数第二级单选 | boolean | — | false |
