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
ms.openlocfilehash: 18e0b7b3547bb246588f6b255483d4c317e0df88
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742231"
---
# <a name="closeassembly-method"></a><span data-ttu-id="9fb79-102">CloseAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="9fb79-102">CloseAssembly Method</span></span>
<span data-ttu-id="9fb79-103">アセンブリの操作を終了します。</span><span class="sxs-lookup"><span data-stu-id="9fb79-103">Finalizes assembly operations.</span></span> <span data-ttu-id="9fb79-104">新しいアセンブリまたはバインドされていないモジュールを開始する前に、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9fb79-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fb79-105">構文</span><span class="sxs-lookup"><span data-stu-id="9fb79-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fb79-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9fb79-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9fb79-107">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="9fb79-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fb79-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="9fb79-108">Return Value</span></span>  
 <span data-ttu-id="9fb79-109">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="9fb79-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fb79-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="9fb79-110">Requirements</span></span>  
 <span data-ttu-id="9fb79-111">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="9fb79-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fb79-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fb79-112">See also</span></span>

- [<span data-ttu-id="9fb79-113">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9fb79-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9fb79-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9fb79-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9fb79-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="9fb79-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
