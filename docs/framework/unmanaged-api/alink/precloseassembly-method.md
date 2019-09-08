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
ms.openlocfilehash: d4cf862ae3676b85a7fc3f09a4f5794e01284737
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787238"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="691ab-102">PreCloseAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="691ab-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="691ab-103">アセンブリファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="691ab-103">Closes the assembly file.</span></span> <span data-ttu-id="691ab-104">他のすべてのファイルを閉じた後、アセンブリファイルを閉じる前に、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="691ab-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="691ab-105">バインドされていないモジュールに対しては、このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="691ab-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="691ab-106">構文</span><span class="sxs-lookup"><span data-stu-id="691ab-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="691ab-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="691ab-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="691ab-108">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="691ab-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="691ab-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="691ab-109">Return Value</span></span>  
 <span data-ttu-id="691ab-110">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="691ab-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="691ab-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="691ab-111">Requirements</span></span>  
 <span data-ttu-id="691ab-112">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="691ab-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="691ab-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="691ab-113">See also</span></span>

- [<span data-ttu-id="691ab-114">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="691ab-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="691ab-115">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="691ab-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="691ab-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="691ab-116">ALink API</span></span>](index.md)
