---
title: アセンブリ '<assembly1>' からの間接参照により、埋め込まれた相互運用機能アセンブリ '<assembly2>' の参照が作成されました。
ms.date: 07/20/2015
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
ms.openlocfilehash: 36ae9d8257c8265b813bba446f685428bbf0b1e7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646885"
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-assembly1-because-of-an-indirect-reference-to-that-assembly-from-assembly-assembly2"></a><span data-ttu-id="d885d-102">埋め込まれた相互運用機能アセンブリへの参照が作成された '\<assembly1 >' のアセンブリからそのアセンブリへの間接参照により'\<assembly2 >'</span><span class="sxs-lookup"><span data-stu-id="d885d-102">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'</span></span>
<span data-ttu-id="d885d-103">埋め込まれた相互運用機能アセンブリ '\<assembly1>' への参照が作成されました。これは、そのアセンブリへの間接参照がアセンブリ '\<assembly2>' によって作成されたためです。</span><span class="sxs-lookup"><span data-stu-id="d885d-103">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'.</span></span> <span data-ttu-id="d885d-104">両方のアセンブリで '相互運用機能型の埋め込み' プロパティを変更することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d885d-104">Consider changing the 'Embed Interop Types' property on either assembly.</span></span>  
  
 <span data-ttu-id="d885d-105">`Embed Interop Types` プロパティが `True` に設定されたアセンブリ (assembly1) に参照を追加しました。</span><span class="sxs-lookup"><span data-stu-id="d885d-105">You have added a reference to an assembly (assembly1) that has the `Embed Interop Types` property set to `True`.</span></span> <span data-ttu-id="d885d-106">これにより、コンパイラは、このアセンブリから相互運用機能の型情報を埋め込むよう指示されます。</span><span class="sxs-lookup"><span data-stu-id="d885d-106">This instructs the compiler to embed interop type information from that assembly.</span></span> <span data-ttu-id="d885d-107">ただし、参照していた別のアセンブリ (assembly2) もこのアセンブリ (assembly1) を参照しており、また `Embed Interop Types` プロパティが `False` に設定されているため、コンパイラはこのアセンブリから相互運用機能の型情報を埋め込むことができません。</span><span class="sxs-lookup"><span data-stu-id="d885d-107">However, the compiler cannot embed interop type information from that assembly because another assembly that you have referenced (assembly2) also references that assembly (assembly1) and has the `Embed Interop Types` property set to `False`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d885d-108">アセンブリ参照の `Embed Interop Types` プロパティを `True` に設定することは、コマンド ライン コンパイラの `/link` オプションを使用してアセンブリを参照することと同じです。</span><span class="sxs-lookup"><span data-stu-id="d885d-108">Setting the `Embed Interop Types` property on an assembly reference to `True` is equivalent to referencing the assembly by using the `/link` option for the command-line compiler.</span></span>  
  
 <span data-ttu-id="d885d-109">**エラー ID:** BC40059</span><span class="sxs-lookup"><span data-stu-id="d885d-109">**Error ID:** BC40059</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="d885d-110">この警告に対処するには</span><span class="sxs-lookup"><span data-stu-id="d885d-110">To address this warning</span></span>  
  
- <span data-ttu-id="d885d-111">両方のアセンブリに相互運用の型情報を埋め込むには、assembly1 へのすべての参照の `Embed Interop Types` プロパティを `True` に設定します。</span><span class="sxs-lookup"><span data-stu-id="d885d-111">To embed interop type information for both assemblies, set the `Embed Interop Types` property on all references to assembly1 to `True`.</span></span>  
  
- <span data-ttu-id="d885d-112">assembly1 の `Embed Interop Types` プロパティを `False` に設定すると警告を回避できます。</span><span class="sxs-lookup"><span data-stu-id="d885d-112">To remove the warning, you can set the `Embed Interop Types` property of assembly1 to `False`.</span></span> <span data-ttu-id="d885d-113">この場合は、相互運用機能型の情報は、プライマリ相互運用機能アセンブリ (PIA) によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="d885d-113">In this case, interop type information is provided by a primary interop assembly (PIA).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d885d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d885d-114">See also</span></span>

- [<span data-ttu-id="d885d-115">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d885d-115">/link (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="d885d-116">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="d885d-116">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
