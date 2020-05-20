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
ms.openlocfilehash: aae03b0dc76639c50f4615d41eef73990226b5f7
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442125"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="ecaf6-102">IDebugAutoAttach::AutoAttach メソッド</span><span class="sxs-lookup"><span data-stu-id="ecaf6-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="ecaf6-103">サーバーによって呼び出されたデバッガーの自動アタッチを実行します。</span><span class="sxs-lookup"><span data-stu-id="ecaf6-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecaf6-104">構文</span><span class="sxs-lookup"><span data-stu-id="ecaf6-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ecaf6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ecaf6-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="ecaf6-106">から常にに設定 `GUID_NULL` します。</span><span class="sxs-lookup"><span data-stu-id="ecaf6-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="ecaf6-107">からプロセス ID。通常は関数を使用して取得さ `GetCurrentProcessId` れます。</span><span class="sxs-lookup"><span data-stu-id="ecaf6-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="ecaf6-108">からプログラムの種類: `AUTOATTACH_PROGRAM_WIN32` 、 `AUTOATTACH_PROGRAM_COMPLUS` 、または `AUTOATTACH_PROGRAM_UNKNOWN` 。</span><span class="sxs-lookup"><span data-stu-id="ecaf6-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="ecaf6-109">からプログラム ID。</span><span class="sxs-lookup"><span data-stu-id="ecaf6-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="ecaf6-110">からデバッグ動詞によって渡された文字列。</span><span class="sxs-lookup"><span data-stu-id="ecaf6-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecaf6-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="ecaf6-111">Return Value</span></span>  
 <span data-ttu-id="ecaf6-112">メソッドが成功した場合は S_OK します。</span><span class="sxs-lookup"><span data-stu-id="ecaf6-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecaf6-113">要件</span><span class="sxs-lookup"><span data-stu-id="ecaf6-113">Requirements</span></span>  
 <span data-ttu-id="ecaf6-114">**ヘッダー:** DbgAutoAttach .h</span><span class="sxs-lookup"><span data-stu-id="ecaf6-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecaf6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecaf6-115">See also</span></span>

- [<span data-ttu-id="ecaf6-116">IDebugAutoAttach インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ecaf6-116">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)
