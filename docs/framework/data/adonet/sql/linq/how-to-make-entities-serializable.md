---
title: '方法: エンティティをシリアル化可能にする'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: 40a0b4d5a49f88af1bedcbefdd117f6c000b791d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793568"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="99e55-102">方法: エンティティをシリアル化可能にする</span><span class="sxs-lookup"><span data-stu-id="99e55-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="99e55-103">コードを作成するときに、エンティティをシリアル化可能にできます。</span><span class="sxs-lookup"><span data-stu-id="99e55-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="99e55-104">エンティティ クラスは <xref:System.Runtime.Serialization.DataContractAttribute> 属性で装飾し、列は <xref:System.Runtime.Serialization.DataMemberAttribute> 属性で装飾します。</span><span class="sxs-lookup"><span data-stu-id="99e55-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="99e55-105">Visual Studio を使用する開発者は、この目的のためにオブジェクトリレーショナルデザイナーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="99e55-105">Developers using Visual Studio can use the Object Relational Designer for this purpose.</span></span>  
  
 <span data-ttu-id="99e55-106">SQLMetal コマンドラインツールを使用している場合は、 **/シリアル化**オプションを`unidirectional`引数と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="99e55-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="99e55-107">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="99e55-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99e55-108">例</span><span class="sxs-lookup"><span data-stu-id="99e55-108">Example</span></span>  
 <span data-ttu-id="99e55-109">次の SQLMetal コマンド ラインでは、シリアル化可能なエンティティを持つファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="99e55-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="99e55-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="99e55-110">See also</span></span>

- [<span data-ttu-id="99e55-111">シリアル化</span><span class="sxs-lookup"><span data-stu-id="99e55-111">Serialization</span></span>](serialization.md)
- [<span data-ttu-id="99e55-112">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="99e55-112">Creating the Object Model</span></span>](creating-the-object-model.md)
