---
title: ISymUnmanagedWriter5 インターフェイス
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: d9204457b71b670e1c96ed228ad11116bdf41fe6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493579"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="6a961-102">ISymUnmanagedWriter5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a961-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="6a961-103">ISymUnmanagedWriter5 インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6a961-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a961-104">構文</span><span class="sxs-lookup"><span data-stu-id="6a961-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="6a961-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6a961-105">Methods</span></span>  
 <span data-ttu-id="6a961-106">このインターフェイスには、次のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6a961-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="6a961-107">Method</span><span class="sxs-lookup"><span data-stu-id="6a961-107">Method</span></span>|<span data-ttu-id="6a961-108">説明</span><span class="sxs-lookup"><span data-stu-id="6a961-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a961-109">CloseMapTokensToSourceSpans メソッド</span><span class="sxs-lookup"><span data-stu-id="6a961-109">CloseMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="6a961-110">トークンとソースの間のマッピング情報については、特別なカスタムデータセクションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6a961-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="6a961-111">閉じた後は、マッピング情報を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="6a961-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="6a961-112">MapTokenToSourceSpan メソッド</span><span class="sxs-lookup"><span data-stu-id="6a961-112">MapTokenToSourceSpan Method</span></span>](isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="6a961-113">指定されたメタデータトークンを、指定されたソースファイル内の指定されたソース行スパンにマップします。</span><span class="sxs-lookup"><span data-stu-id="6a961-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="6a961-114">[Openmaptokenstosourcespans メソッド](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)と[CloseMapTokensToSourceSpans メソッド](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)の呼び出しの間で、を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a961-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="6a961-115">OpenMapTokensToSourceSpans メソッド</span><span class="sxs-lookup"><span data-stu-id="6a961-115">OpenMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="6a961-116">特別なカスタムデータセクションを開き、トークンからソースまでの範囲マッピング情報をに出力します。</span><span class="sxs-lookup"><span data-stu-id="6a961-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="6a961-117">メソッドが既に開いている場合や、その逆の場合にこのセクションを開くと、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="6a961-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a961-118">要件</span><span class="sxs-lookup"><span data-stu-id="6a961-118">Requirements</span></span>  
 <span data-ttu-id="6a961-119">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="6a961-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a961-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a961-120">See also</span></span>

- [<span data-ttu-id="6a961-121">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a961-121">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="6a961-122">ISymUnmanagedWriter4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a961-122">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
