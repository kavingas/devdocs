---
group: ui-components-guide
title: FileUploader component
migrated_to: https://developer.adobe.com/commerce/frontend-core/ui-components/components/file-uploader/
layout: migrated
---

The File Uploader component is an [adapter](https://glossary.magento.com/adapter) for the [jQuery-File-Upload](https://github.com/blueimp/jQuery-File-Upload/wiki) plugin used in Magento. This component integrates file upload functionality with UI components.

## Configuration options

| Title | Description | Type | Default Value |
| --- | --- | --- | --- |
| `allowedExtensions` | List of allowed file extensions. For example, `'jpg jpeg gif png svg'`. If set to "false" - then no extension is allowed, "true" - any extension is allowed. | Boolean/String | `false` |
| `component` | The path to the component’s JS constructor in terms of RequireJS. | String | `'Magento_Ui/js/form/element/file-uploader'` |
| `dropZone` | CSS selector of a drop zone element. | String | `[data-role=drop-zone]` |
| `isMultipleFiles` | Defines whether multiple files can be uploaded. | Boolean | `false` |
| `maxFileSize` | Defines the maximum allowed file size in bytes. | Boolean/Number | `false` |
| `placeholderType` | Defines the preview type. (When set to `document`, the file information is displayed.) | `document` \| `image` \| `video` | `document` |
| `previewTmpl` | Path to the file's preview `.html` template | String | `ui/form/element/uploader/preview` |
| `uploaderConfig` | Configuration passed to jquery-file-upload plugin. | Object | `{dataType: 'json', sequentialUploads: true, formData: {'form_key': window.FORM_KEY}}` |

## Examples {#example}

### Integrate FileUploader component with Form component

Here is an example of how File Uploader component integrates with [Form]({{ page.baseurl }}/ui_comp_guide/components/ui-form.html) component:

```xml
<form xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    ...
    <fieldset name="foo">
        ...
        <settings>
            <label translate="true">Foo</label>
            <collapsible>true</collapsible>
            <opened>true</opened>
        </settings>
        <field name="bar" formElement="fileUploader">
            <settings>
                <label translate="true">Sound Check</label>
            </settings>
            <formElements>
                <fileUploader>
                    <settings>
                        <uploaderConfig>
                            <param xsi:type="string" name="url">path/to/controller</param>
                        </uploaderConfig>
                    </settings>
                </fileUploader>
            </formElements>
        </field>
    </fieldset>
</form>
```

### Result

![FileUploader Component example]({{ site.baseurl }}/common/images/ui_comps/ui-fileuploader-result.png)

## Source files

Extends `abstract`:

-  [`<Magento_Ui_module_dir>/view/base/web/js/form/element/file-uploader.js`]({{ site.mage2bloburl }}/{{ page.guide_version }}/app/code/Magento/Ui/view/base/web/js/form/element/file-uploader.js)
-  [`jquery/fileUploader/jquery.fileupload-fp`]({{ site.mage2bloburl }}/{{ page.guide_version }}/lib/web/jquery/fileUploader/jquery.fileupload-fp.js)
-  [`<Magento_Ui_module_dir>/view/base/web/templates/form/element/uploader/uploader.html`]({{ site.mage2bloburl }}/{{ page.guide_version }}/app/code/Magento/Ui/view/base/web/templates/form/element/uploader/uploader.html)
-  [`<Magento_Ui_module_dir>/view/base/web/templates/form/element/uploader/preview.html`]({{ site.mage2bloburl }}/{{ page.guide_version }}/app/code/Magento/Ui/view/base/web/templates/form/element/uploader/preview.html)
