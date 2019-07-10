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
ms.openlocfilehash: a820d5d742c722b495a5a4b3952450a0434110fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741553"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="df0b1-102">PreCloseAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="df0b1-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="df0b1-103">アセンブリ ファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="df0b1-103">Closes the assembly file.</span></span> <span data-ttu-id="df0b1-104">その他のすべてのファイルを閉じた後がアセンブリ ファイルを閉じる前に、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="df0b1-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="df0b1-105">非バインド モジュールのこのメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="df0b1-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df0b1-106">構文</span><span class="sxs-lookup"><span data-stu-id="df0b1-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="df0b1-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df0b1-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="df0b1-108">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="df0b1-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df0b1-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="df0b1-109">Return Value</span></span>  
 <span data-ttu-id="df0b1-110">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="df0b1-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df0b1-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="df0b1-111">Requirements</span></span>  
 <span data-ttu-id="df0b1-112">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="df0b1-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df0b1-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="df0b1-113">See also</span></span>

- [<span data-ttu-id="df0b1-114">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df0b1-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="df0b1-115">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df0b1-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="df0b1-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="df0b1-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
