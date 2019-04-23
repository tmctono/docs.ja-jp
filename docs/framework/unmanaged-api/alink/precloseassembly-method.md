---
title: PreCloseAssembly メソッド
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aab42e939651d75b1933962d72ba8bec1090f52d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184510"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="e10f0-102">PreCloseAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="e10f0-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="e10f0-103">アセンブリ ファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e10f0-103">Closes the assembly file.</span></span> <span data-ttu-id="e10f0-104">その他のすべてのファイルを閉じた後がアセンブリ ファイルを閉じる前に、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e10f0-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="e10f0-105">非バインド モジュールのこのメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="e10f0-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e10f0-106">構文</span><span class="sxs-lookup"><span data-stu-id="e10f0-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e10f0-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e10f0-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e10f0-108">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="e10f0-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e10f0-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="e10f0-109">Return Value</span></span>  
 <span data-ttu-id="e10f0-110">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="e10f0-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e10f0-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="e10f0-111">Requirements</span></span>  
 <span data-ttu-id="e10f0-112">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="e10f0-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e10f0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e10f0-113">See also</span></span>

- [<span data-ttu-id="e10f0-114">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e10f0-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e10f0-115">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e10f0-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e10f0-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="e10f0-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
