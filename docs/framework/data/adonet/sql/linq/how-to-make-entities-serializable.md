---
title: '方法: エンティティをシリアル化可能にする'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: fd687ba5dce16baee063f1d3bb9521c6664988b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743276"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="e11d4-102">方法: エンティティをシリアル化可能にする</span><span class="sxs-lookup"><span data-stu-id="e11d4-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="e11d4-103">コードを作成するときに、エンティティをシリアル化可能にできます。</span><span class="sxs-lookup"><span data-stu-id="e11d4-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="e11d4-104">エンティティ クラスは <xref:System.Runtime.Serialization.DataContractAttribute> 属性で装飾し、列は <xref:System.Runtime.Serialization.DataMemberAttribute> 属性で装飾します。</span><span class="sxs-lookup"><span data-stu-id="e11d4-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="e11d4-105">Visual Studio を使用している開発者は、この目的に、オブジェクト リレーショナル デザイナーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e11d4-105">Developers using Visual Studio can use the Object Relational Designer for this purpose.</span></span>  
  
 <span data-ttu-id="e11d4-106">SQLMetal コマンド ライン ツールを使用している場合は、使用、 **/serialization**オプションは、`unidirectional`引数。</span><span class="sxs-lookup"><span data-stu-id="e11d4-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="e11d4-107">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e11d4-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e11d4-108">例</span><span class="sxs-lookup"><span data-stu-id="e11d4-108">Example</span></span>  
 <span data-ttu-id="e11d4-109">次の SQLMetal コマンド ラインでは、シリアル化可能なエンティティを持つファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e11d4-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="e11d4-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e11d4-110">See also</span></span>

- [<span data-ttu-id="e11d4-111">シリアル化</span><span class="sxs-lookup"><span data-stu-id="e11d4-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)
- [<span data-ttu-id="e11d4-112">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="e11d4-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
