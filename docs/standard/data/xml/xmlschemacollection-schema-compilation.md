---
title: XmlSchemaCollection 架构编译
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
ms.openlocfilehash: af6df3729f1bd926e9a47cc5b9d9bf460c8e1225
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159281"
---
# <a name="xmlschemacollection-schema-compilation"></a>XmlSchemaCollection 架构编译
XmlSchemaCollection 是可用于存储和验证 XML 数据缩减 (XDR) 和 XML 架构定义语言 (XSD) 架构的缓存或库。 XmlSchemaCollection 在内存中缓存架构，而不是通过文件或 URL 访问架构，从而提升了性能。  
  
> [!NOTE]
> 尽管 XmlSchemaCollection 类存储 XDR 架构和 XML 架构，但任何需要使用或返回 XmlSchema 对象的方法和属性都只支持 XML 架构。  
  
> [!IMPORTANT]
> 现在，<xref:System.Xml.Schema.XmlSchemaCollection> 类已过时，已由 <xref:System.Xml.Schema.XmlSchemaSet> 类所取代。 若要详细了解 <xref:System.Xml.Schema.XmlSchemaSet> 类，请参阅[用于编译架构的 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)。  
  
## <a name="add-schemas-to-the-collection"></a>向集合中添加架构  
 架构是使用 XmlSchemaCollection 的 Add 方法在集合中加载，此时架构与命名空间 URI 相关联。 对于 XML 架构，命名空间 URI 通常是该架构的目标命名空间。 对于 XDR 架构，命名空间 URI 是在将架构添加到集合时指定的命名空间。  
  
## <a name="check-for-a-schema-in-the-collection"></a>检查集合中是否存在架构  
 通过使用 Contains 方法，可以检查架构是否位于集合中。 Contains 方法需要使用 XmlSchema 对象（仅对于 XML 架构），或表示与架构关联的命名空间 URI 的字符串（对于 XML 架构和 XDR 架构）。  
  
## <a name="retrieve-a-schema-from-the-collection"></a>从集合中检索架构  
 通过使用 Item 属性，可以从集合中检索架构。 Item 属性需要使用表示与架构关联的命名空间 URI 的字符串（通常是它的目标命名空间），并返回 XmlSchema 对象。 Item 属性仅适用于 XML 架构。 对于 XDR 架构，返回值总是空引用，因为它们没有可用的对象模型。  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a>使用 XmlSchemaCollection 验证 XML 文档  
 可以使用 XmlSchemaCollection 验证 XML 实例文档，具体操作是创建 XmlSchemaCollection 对象，将架构添加到集合中，再设置 XmlValidatingReader 的 Schemas 属性，以将创建的 XmlSchemaCollection 分配给 XmlValidatingReader。  
  
### <a name="improved-performance"></a>提高的性能  
 若要针对相同架构验证多个文档，建议使用 XmlSchemaCollection，因为它在内存中缓存架构，从而提升了性能。  
  
 下面的代码示例创建 XmlSchemaCollection 对象，将架构添加到集合中，并设置 Schemas 属性。  
  
```vb  
Dim tr as XmlTextReader = new XmlTextReader("Books.xml")  
Dim vr as XmlValidatingReader = new XmlValidatingReader(tr)  
Dim xsc as XmlSchemaCollection = new XmlSchemaCollection  
xsc.Add("urn:bookstore-schema", "Books.xsd")  
vr.Schemas.Add(xsc)  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("Books.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
xsc.Add("urn:bookstore-schema", "Books.xsd");
vr.Schemas.Add(xsc);  
```  
  
## <a name="see-also"></a>另请参阅

- [使用 XmlSchemaCollection 进行 XDR 验证](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)
- [使用 XmlSchemaCollection 进行 XML 架构 (XSD) 验证](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
