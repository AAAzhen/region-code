# 国家行政区划以及代码数据库

#### 介绍
此仓库提供国家行政区划及相应代码，所有数据来自[中国·国家地名信息库](https://dmfw.mca.gov.cn/index.html)


数据采集日期：2026年5月6日


#### 软件架构
本脚本支持mysql数据库，其他数据库有待尝试。


#### 安装教程

直接将sql文件下载下来，在数据库中运行即可。

#### 数据样例
```

-- ----------------------------
-- Table structure for sys_region
-- ----------------------------
DROP TABLE IF EXISTS `sys_region`;
CREATE TABLE `sys_region`  (
  `id` int NOT NULL AUTO_INCREMENT COMMENT '主键ID',
  `code` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL COMMENT '地区编码',
  `name` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL COMMENT '名称',
  `path` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL COMMENT '路径',
  `parent_code` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL COMMENT '父级编码',
  `level` int NOT NULL COMMENT '级别',
  `type` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL COMMENT '类型',
  `status` tinyint NOT NULL DEFAULT 1 COMMENT '状态，0-无效，1-有效(默认)',
  `create_time` datetime NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `update_time` datetime NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
  PRIMARY KEY (`id`) USING BTREE,
  UNIQUE INDEX `uk_code`(`code` ASC) USING BTREE,
  INDEX `idx_parent_code`(`parent_code` ASC) USING BTREE
) ENGINE = InnoDB AUTO_INCREMENT = 42645 CHARACTER SET = utf8mb4 COLLATE = utf8mb4_0900_ai_ci COMMENT = '全国行政区划表' ROW_FORMAT = Dynamic;

-- ----------------------------
-- Records of sys_region
-- ----------------------------
INSERT INTO `sys_region` VALUES (1, '00', '全国', ' ', ' ', 0, ' ', 1, '2026-05-06 11:07:03', '2026-05-06 11:07:03');
INSERT INTO `sys_region` VALUES (2, '11', '北京市', ' /北京市', '00', 1, '直辖市', 1, '2026-05-06 11:07:03', '2026-05-06 11:07:03');
INSERT INTO `sys_region` VALUES (3, '110101', '东城区', ' /北京市/东城区', '11', 3, '市辖区', 1, '2026-05-06 11:07:03', '2026-05-06 15:04:37');
INSERT INTO `sys_region` VALUES (4, '110102', '西城区', ' /北京市/西城区', '11', 3, '市辖区', 1, '2026-05-06 11:07:03', '2026-05-06 15:04:37');
INSERT INTO `sys_region` VALUES (5, '110105', '朝阳区', ' /北京市/朝阳区', '11', 3, '市辖区', 1, '2026-05-06 11:07:03', '2026-05-06 15:04:37');
INSERT INTO `sys_region` VALUES (6, '110106', '丰台区', ' /北京市/丰台区', '11', 3, '市辖区', 1, '2026-05-06 11:07:03', '2026-05-06 15:04:37');
INSERT INTO `sys_region` VALUES (7, '110107', '石景山区', ' /北京市/石景山区', '11', 3, '市辖区', 1, '2026-05-06 11:07:03', '2026-05-06 15:04:37');
INSERT INTO `sys_region` VALUES (8, '110108', '海淀区', ' /北京市/海淀区', '11', 3, '市辖区', 1, '2026-05-06 11:07:03', '2026-05-06 15:04:37');
INSERT INTO `sys_region` VALUES (9, '110109', '门头沟区', ' /北京市/门头沟区', '11', 3, '市辖区', 1, '2026-05-06 11:07:03', '2026-05-06 15:04:37');
INSERT INTO `sys_region` VALUES (10, '110111', '房山区', ' /北京市/房山区', '11', 3, '市辖区', 1, '2026-05-06 11:07:03', '2026-05-06 15:04:37');
INSERT INTO `sys_region` VALUES (11, '110112', '通州区', ' /北京市/通州区', '11', 3, '市辖区', 1, '2026-05-06 11:07:03', '2026-05-06 15:04:37');


```
