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
ms.openlocfilehash: c196bcc159b18b9dc04329d817ebe16e07bb8bb7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218252"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="b546b-102">EmitInternalExportedTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="b546b-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="b546b-103">アセンブリに追加された型を出力します。</span><span class="sxs-lookup"><span data-stu-id="b546b-103">Emits types added to the assembly.</span></span> <span data-ttu-id="b546b-104">既知の内部型が追加された後は、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b546b-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b546b-105">構文</span><span class="sxs-lookup"><span data-stu-id="b546b-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b546b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b546b-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b546b-107">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="b546b-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b546b-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="b546b-108">Return Value</span></span>  
 <span data-ttu-id="b546b-109">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="b546b-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b546b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b546b-110">Requirements</span></span>  
 <span data-ttu-id="b546b-111">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="b546b-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b546b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b546b-112">See also</span></span>

- [<span data-ttu-id="b546b-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b546b-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b546b-114">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b546b-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b546b-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="b546b-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
