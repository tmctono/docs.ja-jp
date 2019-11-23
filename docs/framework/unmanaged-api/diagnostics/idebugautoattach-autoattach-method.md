---
title: IDebugAutoAttach::AutoAttach メソッド
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
ms.openlocfilehash: 766aeb31436101babeab31b615a1c633578bfcc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445526"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="75989-102">IDebugAutoAttach::AutoAttach メソッド</span><span class="sxs-lookup"><span data-stu-id="75989-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="75989-103">Performs server-invoked debugger auto attach.</span><span class="sxs-lookup"><span data-stu-id="75989-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75989-104">構文</span><span class="sxs-lookup"><span data-stu-id="75989-104">Syntax</span></span>  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75989-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="75989-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="75989-106">[in] Always set to `GUID_NULL`.</span><span class="sxs-lookup"><span data-stu-id="75989-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="75989-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span><span class="sxs-lookup"><span data-stu-id="75989-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="75989-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span><span class="sxs-lookup"><span data-stu-id="75989-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="75989-109">[in] Program ID.</span><span class="sxs-lookup"><span data-stu-id="75989-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="75989-110">[in] String passed by the debug verb.</span><span class="sxs-lookup"><span data-stu-id="75989-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75989-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="75989-111">Return Value</span></span>  
 <span data-ttu-id="75989-112">S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="75989-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75989-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="75989-113">Requirements</span></span>  
 <span data-ttu-id="75989-114">**Header:** DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="75989-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75989-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="75989-115">See also</span></span>

- [<span data-ttu-id="75989-116">IDebugAutoAttach インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75989-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
