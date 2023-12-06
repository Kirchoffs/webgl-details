# Notes

## Difference between Uniform and Attribute
Uniform
- Global Scope: Uniforms are global GLSL variables. They act as constants during a single draw call. This means their values are set before the draw call and remain constant for all vertices and fragments processed in that call.
- Purpose: They are typically used to pass data that is uniform across all vertices and fragments processed by the shader, such as transformation matrices, light information, or global settings.
- Modification: Their values are set from the WebGL JavaScript code and cannot be altered by the GLSL shader code during a draw call.
- Shared Across Vertices and Fragments: The same uniform can be accessed from both vertex and fragment shaders.

Attribute
- Vertex-Specific: Attributes are associated with individual vertices. They are used to pass data that varies per vertex, such as vertex coordinates, normals, texture coordinates, and colors.
- Purpose: They provide a way to feed per-vertex data into the vertex shader. Each vertex can have its own unique set of attribute values.
- Buffer Binding: In WebGL, attributes are typically set by binding a buffer containing the vertex data and using commands like gl.vertexAttribPointer() to tell WebGL how to extract the attribute data from the buffer.
- Used in Vertex Shaders: Attributes are only available in the vertex shader. They cannot be directly accessed in the fragment shader. However, data from attributes can be passed to the fragment shader through varying variables.