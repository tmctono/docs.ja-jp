---
title: CloseAssembly メソッド
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7828c86018724bb934de99cab4617f9885fdca6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787607"
---
# <a name="closeassembly-method"></a><span data-ttu-id="5b199-102">CloseAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="5b199-102">CloseAssembly Method</span></span>
<span data-ttu-id="5b199-103">アセンブリ操作を終了します。</span><span class="sxs-lookup"><span data-stu-id="5b199-103">Finalizes assembly operations.</span></span> <span data-ttu-id="5b199-104">新しいアセンブリまたは非バインドモジュールを開始する前に、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5b199-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b199-105">構文</span><span class="sxs-lookup"><span data-stu-id="5b199-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b199-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b199-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5b199-107">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="5b199-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b199-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5b199-108">Return Value</span></span>  
 <span data-ttu-id="5b199-109">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="5b199-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b199-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="5b199-110">Requirements</span></span>  
 <span data-ttu-id="5b199-111">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="5b199-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b199-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b199-112">See also</span></span>

- [<span data-ttu-id="5b199-113">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b199-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5b199-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b199-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5b199-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="5b199-115">ALink API</span></span>](index.md)
