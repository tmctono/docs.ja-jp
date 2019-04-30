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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5064e66708044d82e3a097c8235b5b28a3412200
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986493"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="667c5-102">IDebugAutoAttach::AutoAttach メソッド</span><span class="sxs-lookup"><span data-stu-id="667c5-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="667c5-103">サーバー起動デバッガーの自動実行をアタッチします。</span><span class="sxs-lookup"><span data-stu-id="667c5-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="667c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="667c5-104">Syntax</span></span>  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="667c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="667c5-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="667c5-106">[in]常に設定`GUID_NULL`します。</span><span class="sxs-lookup"><span data-stu-id="667c5-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="667c5-107">[in]プロセス ID で通常取得、`GetCurrentProcessId`関数。</span><span class="sxs-lookup"><span data-stu-id="667c5-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="667c5-108">[in]プログラムの種類: `AUTOATTACH_PROGRAM_WIN32`、 `AUTOATTACH_PROGRAM_COMPLUS`、または`AUTOATTACH_PROGRAM_UNKNOWN`します。</span><span class="sxs-lookup"><span data-stu-id="667c5-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="667c5-109">[in]プログラム id。</span><span class="sxs-lookup"><span data-stu-id="667c5-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="667c5-110">[in]Debug 動詞によって渡された文字列。</span><span class="sxs-lookup"><span data-stu-id="667c5-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="667c5-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="667c5-111">Return Value</span></span>  
 <span data-ttu-id="667c5-112">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="667c5-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="667c5-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="667c5-113">Requirements</span></span>  
 <span data-ttu-id="667c5-114">**ヘッダー:** DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="667c5-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="667c5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="667c5-115">See also</span></span>

- [<span data-ttu-id="667c5-116">IDebugAutoAttach インターフェイス</span><span class="sxs-lookup"><span data-stu-id="667c5-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
