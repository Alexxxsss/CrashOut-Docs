---
description: A efficient system that has enteties, components and functionality
icon: cube
---

# ECS

***

The system is designed to support a large number of objects without duplicating functionality code. The components are simply data stored inside structs that are attached to the entities, which are just IDs, and the functionality then processes and executes this data. To maximize efficiency, the functionality processes all objects with a given component simultaneously.

```cpp
///  Variables for entity, model and material
Entity entity1;
std::shared_ptr<Model> cubeModel;
std::shared_ptr<Material> brickMaterial;

///  Initialize .obj model and .png texture
cubeModel = std::make_shared<Model>();
cubeModel->Init(&GetRenderer());
cubeModel->Create("Cube.obj");

brickMaterial = std::make_shared<Material>();
brickMaterial->Init(&GetRenderer());
brickMaterial->LoadTexture(L"Brick.png");


///  Initializing the Entity
///  Adding the componments to the Entity
entity2 = myRegistry.CreateEntity();
myRegistry.AddComponent<TransformComponent>(entity2);
myRegistry.AddComponent<MeshComponent>(entity2, cubeModel);
myRegistry.AddComponent<MaterialComponent>(entity2, brickMaterial);
myRegistry.AddComponent<BoxColliderComponent>(entity2);

```
