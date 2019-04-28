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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790014"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="ea1eb-102">EmitInternalExportedTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="ea1eb-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="ea1eb-103">アセンブリに追加された型を出力します。</span><span class="sxs-lookup"><span data-stu-id="ea1eb-103">Emits types added to the assembly.</span></span> <span data-ttu-id="ea1eb-104">既知の内部型が追加された後は、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ea1eb-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea1eb-105">構文</span><span class="sxs-lookup"><span data-stu-id="ea1eb-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea1eb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea1eb-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ea1eb-107">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="ea1eb-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea1eb-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="ea1eb-108">Return Value</span></span>  
 <span data-ttu-id="ea1eb-109">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="ea1eb-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea1eb-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ea1eb-110">Requirements</span></span>  
 <span data-ttu-id="ea1eb-111">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="ea1eb-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea1eb-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea1eb-112">See also</span></span>

- [<span data-ttu-id="ea1eb-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea1eb-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ea1eb-114">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea1eb-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ea1eb-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="ea1eb-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
