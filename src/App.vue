<!-- App.vue -->

<template>
    <div id="app">
        <ckeditor :editor="editor" v-model="editorData" :config="editorConfig"></ckeditor>
    </div>
</template>

<script>
    // Since we're building CKEditor 5 from source, we use the source version of ClassicEditor.
    import { ClassicEditor } from '@ckeditor/ckeditor5-editor-classic';

    import { Essentials } from '@ckeditor/ckeditor5-essentials';
    import { Bold, Italic } from '@ckeditor/ckeditor5-basic-styles';
    import { Link } from '@ckeditor/ckeditor5-link';
    import { Paragraph } from '@ckeditor/ckeditor5-paragraph';
    import MathType from '@wiris/mathtype-ckeditor5/src/plugin';
  
    export default {
        name: 'app',
        data() {
            return {
                editor: ClassicEditor,
                editorData: '<p>Content of the editor.</p>',
                editorConfig: {
                    plugins: [
                        Essentials,
                        Bold,
                        Italic,
                        Link,
                        Paragraph,
                        MathType
                    ],

                    toolbar: {
                        items: [
                            'bold',
                            'italic',
                            'link',
                            'undo',
                            'redo',
                            'MathType',
                            'ChemType',
                        ]
                    }
                },
            };
        }
    };
</script>
