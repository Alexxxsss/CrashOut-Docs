---
description: A efficient system that has enteties, components and functionality
icon: cube
---

# ECS

***

The system is designed to support a large number of objects without duplicating functionality code. The components are simply data stored inside structs that are attached to the entities, which are just IDs, and the functionality then processes and executes this data. To maximize efficiency, the functionality processes all objects with a given component simultaneously.

<pre class="language-cpp"><code class="lang-cpp">///  Variables for entity, model and material
Entity entity1;
std::shared_ptr&#x3C;Model> cubeModel;
std::shared_ptr&#x3C;Material> brickMaterial;

///  Initialize .obj model and .png texture
cubeModel = std::make_shared&#x3C;Model>();
cubeModel->Init(&#x26;GetRenderer());
cubeModel->Create("Cube.obj");

brickMaterial = std::make_shared&#x3C;Material>();
brickMaterial->Init(&#x26;GetRenderer());
brickMaterial->LoadTexture(L"Brick.png");

<strong>
</strong><strong>///  Initializing the Entity
</strong><strong>///  Adding the componments to the Entity
</strong><strong>entity2 = myRegistry.CreateEntity();
</strong>myRegistry.AddComponent&#x3C;TransformComponent>(entity2);
myRegistry.AddComponent&#x3C;MeshComponent>(entity2, cubeModel);
myRegistry.AddComponent&#x3C;MaterialComponent>(entity2, brickMaterial);
myRegistry.AddComponent&#x3C;BoxColliderComponent>(entity2);

</code></pre>
