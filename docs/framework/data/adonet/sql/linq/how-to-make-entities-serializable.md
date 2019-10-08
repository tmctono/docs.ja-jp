---
title: '方法: エンティティをシリアル化可能にする'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: 5e9d078ed2daacfa48b09693f533e9aade613281
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002713"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="01e05-102">方法: エンティティをシリアル化可能にする</span><span class="sxs-lookup"><span data-stu-id="01e05-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="01e05-103">コードを作成するときに、エンティティをシリアル化可能にできます。</span><span class="sxs-lookup"><span data-stu-id="01e05-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="01e05-104">エンティティ クラスは <xref:System.Runtime.Serialization.DataContractAttribute> 属性で装飾し、列は <xref:System.Runtime.Serialization.DataMemberAttribute> 属性で装飾します。</span><span class="sxs-lookup"><span data-stu-id="01e05-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="01e05-105">Visual Studio を使用する開発者は、この目的のためにオブジェクトリレーショナルデザイナーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="01e05-105">Developers using Visual Studio can use the Object Relational Designer for this purpose.</span></span>  
  
 <span data-ttu-id="01e05-106">SQLMetal コマンドラインツールを使用している場合は、 **/シリアル化**オプションを `unidirectional` 引数と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="01e05-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="01e05-107">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="01e05-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01e05-108">例</span><span class="sxs-lookup"><span data-stu-id="01e05-108">Example</span></span>  
 <span data-ttu-id="01e05-109">次の SQLMetal コマンド ラインでは、シリアル化可能なエンティティを持つファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="01e05-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="01e05-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="01e05-110">See also</span></span>

- [<span data-ttu-id="01e05-111">シリアル化</span><span class="sxs-lookup"><span data-stu-id="01e05-111">Serialization</span></span>](serialization.md)
- [<span data-ttu-id="01e05-112">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="01e05-112">Creating the Object Model</span></span>](creating-the-object-model.md)
