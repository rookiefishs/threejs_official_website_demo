# Three.js 示例项目

一个基于 Three.js 的 WebGL 示例集合，包含动画、相机控制、裁剪等多种 3D 图形技术的实现。

## 项目概述

本项目是一个 Three.js 学习和演示项目，包含了多个 WebGL 示例，涵盖了 3D 动画、相机控制、材质渲染、几何体操作等核心功能。每个示例都是独立的 HTML 文件，可以直接在浏览器中运行。

## 作者信息

- **作者**: WangZhiYu
- **创建时间**: 2023年7月
- **最后更新**: 2023年10月

## 项目结构

```
├── 📁 根目录
│   ├── 🎬 动画示例
│   │   ├── 01-webgl_animation_keyframes.html          # 关键帧动画
│   │   ├── 02-webgl_animation_skinning_blending.html  # 骨骼动画混合
│   │   ├── 03-webgl_animation_skinning_additive_blending.html # 骨骼动画叠加混合
│   │   ├── 04-webgl_animation_skinning_ik.html        # 反向动力学骨骼动画
│   │   ├── 05-webgl_animation_skinning_morph.html     # 变形动画
│   │   └── 06-webgl_animation_multiple.html           # 多重动画
│   │
│   ├── 📷 相机示例
│   │   ├── 07-webgl_camera.html                       # 基础相机控制
│   │   ├── 08-webgl_camera_array.html                 # 相机阵列
│   │   ├── 09-webgl_camera_cinematic.html             # 电影级相机
│   │   └── 10-webgl_camera_logarithmicdepthbuffer.html # 对数深度缓冲
│   │
│   ├── ✂️ 裁剪示例
│   │   ├── 11-webgl_clipping.html                     # 基础裁剪
│   │   └── 12-webgl_clipping_advanced.html            # 高级裁剪
│   │
│   ├── 🎨 样式和模板
│   │   ├── base.css                                   # 基础样式
│   │   ├── template.html                              # 项目模板
│   │   └── 滚动条控制动画进度.html                     # 滚动控制动画
│   │
│   ├── 🔧 核心文件
│   │   └── initThree.js                               # Three.js 初始化类
│   │
│   ├── 📦 Three.js 源码
│   │   └── threeSource/
│   │       ├── three.js                               # 开发版本
│   │       ├── three.min.js                           # 压缩版本
│   │       ├── three.module.js                        # ES6 模块版本
│   │       └── three.cjs                              # CommonJS 版本
│   │
│   ├── 🎭 3D 模型资源
│   │   └── models/                                    # 各种格式的3D模型
│   │       ├── gltf/                                  # GLTF 格式模型
│   │       ├── fbx/                                   # FBX 格式模型
│   │       ├── obj/                                   # OBJ 格式模型
│   │       └── ... (更多格式)
│   │
│   ├── 🔌 Three.js 扩展
│   │   └── public/                                    # Three.js 官方扩展库
│   │       ├── controls/                              # 控制器
│   │       ├── loaders/                               # 加载器
│   │       ├── postprocessing/                        # 后处理效果
│   │       ├── materials/                             # 材质
│   │       └── ... (更多扩展)
│   │
│   └── 🎨 字体资源
│       └── fonts/                                     # 字体文件
```

## 功能特性

### 🎬 动画系统
- **关键帧动画**: 基于时间轴的动画控制
- **骨骼动画**: 支持角色动画和变形
- **动画混合**: 多个动画的平滑过渡
- **反向动力学**: IK 骨骼动画系统
- **变形动画**: Morph Target 动画

### 📷 相机控制
- **轨道控制**: 围绕目标旋转的相机控制
- **第一人称**: FPS 风格的相机控制
- **电影相机**: 专业的电影级相机效果
- **相机阵列**: 多视角渲染
- **深度缓冲**: 对数深度缓冲优化

### ✂️ 几何体操作
- **基础裁剪**: 平面裁剪功能
- **高级裁剪**: 复杂的几何体裁剪
- **实时渲染**: 动态裁剪效果

### 🎨 渲染特性
- **PBR 材质**: 基于物理的渲染
- **环境贴图**: 自动环境光照
- **后处理**: 各种视觉效果
- **阴影系统**: 实时阴影渲染

## 技术栈

- **Three.js**: 3D 图形库
- **WebGL**: 底层图形 API
- **ES6 Modules**: 现代 JavaScript 模块系统
- **GLTF/GLB**: 3D 模型格式
- **Draco**: 几何体压缩

## 快速开始

### 环境要求

- 现代浏览器 (支持 WebGL 和 ES6 Modules)
- 本地服务器 (推荐使用 Live Server 或类似工具)

### 安装运行

1. **克隆项目**
   ```bash
   git clone [项目地址]
   cd threejs-examples
   ```

2. **启动本地服务器**
   ```bash
   # 使用 Python
   python -m http.server 8000
   
   # 或使用 Node.js
   npx serve .
   
   # 或使用 Live Server (VS Code 扩展)
   ```

3. **访问示例**
   ```
   http://localhost:8000/01-webgl_animation_keyframes.html
   ```

### 创建新示例

1. **复制模板文件**
   ```bash
   cp template.html your-new-example.html
   ```

2. **修改示例内容**
   ```javascript
   class CurrentDemo extends InitThree {
     constructor() {
       super({
         initFn() {
           // 初始化配置
           this.option.renderer.setClearColor('#bfe3dd');
         }
       });
       
       // 添加你的代码
       this.render();
     }
   }
   ```

## 核心类说明

### InitThree 类

项目的核心初始化类，提供了 Three.js 的基础功能封装：

```javascript
class InitThree {
  constructor(option) {
    // 配置选项
    this.option = {
      width: window.innerWidth,      // 渲染宽度
      height: window.innerHeight,    // 渲染高度
      scene: new THREE.Scene(),      // 场景
      camera: new THREE.PerspectiveCamera(), // 相机
      renderer: new THREE.WebGL1Renderer(),  // 渲染器
      controls: null,                // 控制器
      root: '#root'                  // DOM 容器
    };
  }
  
  // 主要方法
  initThree(callback)              // 初始化 Three.js 环境
  initExample(modelPath, ...)      // 加载 GLTF 模型
  setCameraPosition(x, y, z)       // 设置相机位置
  render(callback)                 // 渲染循环
  gobalResize(callback)            // 响应式处理
}
```

### 使用示例

```javascript
// 基础使用
class MyDemo extends InitThree {
  constructor() {
    super({
      initFn() {
        // 自定义初始化
        this.option.renderer.setClearColor('#000000');
      }
    });
    
    this.loadModel();
    this.render();
  }
  
  loadModel() {
    this.initExample(
      './models/gltf/model.glb',
      (model) => {
        // 模型加载成功
        this.option.scene.add(model.scene);
      }
    );
  }
}
```

## 示例详解

### 1. 关键帧动画 (01-webgl_animation_keyframes.html)

展示了如何使用 Three.js 的动画系统：

- **AnimationMixer**: 动画混合器
- **AnimationClip**: 动画片段
- **Clock**: 时间控制
- **环境贴图**: 使用 RoomEnvironment

```javascript
// 创建动画混合器
this.mixer = new THREE.AnimationMixer(model.scene);

// 播放动画
this.mixer.clipAction(model.animations[0]).play();

// 在渲染循环中更新
this.mixer.update(delta);
```

### 2. 相机控制 (07-webgl_camera.html)

演示了不同类型的相机控制：

- **OrbitControls**: 轨道控制器
- **相机位置**: 动态调整
- **控制器配置**: 阻尼、平移等

### 3. 几何体裁剪 (11-webgl_clipping.html)

展示了实时几何体裁剪功能：

- **ClippingPlanes**: 裁剪平面
- **Material.clippingPlanes**: 材质裁剪
- **实时更新**: 动态裁剪效果

## 资源文件说明

### 模型格式支持

| 格式 | 描述 | 用途 |
|------|------|------|
| GLTF/GLB | 现代3D格式 | 推荐使用，支持动画、材质 |
| FBX | Autodesk格式 | 复杂动画模型 |
| OBJ | 通用格式 | 静态几何体 |
| STL | 3D打印格式 | 简单几何体 |
| PLY | 点云格式 | 科学可视化 |

### 纹理和材质

- **环境贴图**: HDR 环境光照
- **PBR 材质**: 金属度、粗糙度贴图
- **法线贴图**: 表面细节增强
- **AO 贴图**: 环境光遮蔽

## 性能优化

### 渲染优化

1. **几何体合并**: 减少绘制调用
2. **纹理压缩**: 使用 Draco 压缩
3. **LOD 系统**: 距离级别细节
4. **视锥体剔除**: 自动优化

### 内存管理

```javascript
// 释放资源
geometry.dispose();
material.dispose();
texture.dispose();
renderer.dispose();
```

### 最佳实践

- 使用 `requestAnimationFrame` 进行动画
- 合理设置相机的 near/far 平面
- 避免频繁创建/销毁对象
- 使用对象池管理复用对象

## 浏览器兼容性

| 浏览器 | 版本要求 | WebGL 支持 |
|--------|----------|------------|
| Chrome | 60+ | WebGL 2.0 |
| Firefox | 55+ | WebGL 2.0 |
| Safari | 12+ | WebGL 2.0 |
| Edge | 79+ | WebGL 2.0 |

## 常见问题

### Q: 模型加载失败？
A: 检查模型路径和格式，确保使用本地服务器运行。

### Q: 动画不播放？
A: 确保在渲染循环中调用 `mixer.update(delta)`。

### Q: 性能问题？
A: 检查模型复杂度，使用 Draco 压缩，优化纹理大小。

### Q: 移动端适配？
A: 设置合适的 `devicePixelRatio` 和响应式尺寸。

## 扩展开发

### 添加新功能

1. **自定义材质**
   ```javascript
   const customMaterial = new THREE.ShaderMaterial({
     vertexShader: vertexShaderCode,
     fragmentShader: fragmentShaderCode
   });
   ```

2. **后处理效果**
   ```javascript
   import { EffectComposer } from 'three/addons/postprocessing/EffectComposer.js';
   import { RenderPass } from 'three/addons/postprocessing/RenderPass.js';
   ```

3. **物理引擎集成**
   ```javascript
   import { AmmoPhysics } from 'three/addons/physics/AmmoPhysics.js';
   ```

## 学习资源

- [Three.js 官方文档](https://threejs.org/docs/)
- [Three.js 示例](https://threejs.org/examples/)
- [WebGL 基础教程](https://webglfundamentals.org/)
- [3D 数学基础](https://www.3dgep.com/)

## 贡献指南

1. Fork 项目
2. 创建功能分支
3. 提交更改
4. 发起 Pull Request

## 许可证

本项目采用 MIT 许可证，详见 LICENSE 文件。

## 联系方式

- **作者**: WangZhiYu
- **邮箱**: [联系邮箱]
- **GitHub**: [GitHub 地址]

---

*最后更新: 2024年1月*