# 多模态与 mmproj

## 什么情况下需要 `mmproj`

当你加载的是 `llama.cpp` 兼容的视觉语言模型时，通常除了主模型文件，还需要一个 `mmproj` 文件。

常见形式：

```bash
./omniinfer model load \
  -m /path/to/model.gguf \
  -mm /path/to/mmproj.gguf
```

## 自动发现

如果你把模型组织成目录，并且目录中只有：

- 一个主模型 GGUF
- 一个 `mmproj` GGUF

那么 OmniInfer 可以在目录加载时自动发现它们。

## 图像输入

模型加载完成后，可通过：

```bash
./omniinfer chat \
  --image /path/to/image.jpg \
  --message "Describe this image in one sentence."
```

来发起图文请求。

## 注意事项

- 不是所有 backend 都支持 `mmproj`
- 不是所有模型目录都能自动推断 `mmproj`
- 如果图像请求报错，优先检查当前 backend、模型和 `mmproj` 是否匹配
