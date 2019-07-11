---
title: EmitInternalExportedTypes メソッド
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15174480c4345f2514572701a5525f0f192ad120
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742100"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="40c06-102">EmitInternalExportedTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="40c06-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="40c06-103">アセンブリに追加された型を出力します。</span><span class="sxs-lookup"><span data-stu-id="40c06-103">Emits types added to the assembly.</span></span> <span data-ttu-id="40c06-104">既知の内部型が追加された後は、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="40c06-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40c06-105">構文</span><span class="sxs-lookup"><span data-stu-id="40c06-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="40c06-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40c06-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="40c06-107">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="40c06-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40c06-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="40c06-108">Return Value</span></span>  
 <span data-ttu-id="40c06-109">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="40c06-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40c06-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="40c06-110">Requirements</span></span>  
 <span data-ttu-id="40c06-111">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="40c06-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c06-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="40c06-112">See also</span></span>

- [<span data-ttu-id="40c06-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40c06-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="40c06-114">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40c06-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="40c06-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="40c06-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
