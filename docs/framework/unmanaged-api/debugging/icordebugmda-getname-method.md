---
title: ICorDebugMDA::GetName メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
ms.openlocfilehash: 6a6769265a2e140f1fa001bb8240bc5d4bd76018
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213674"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="2e3a1-102">ICorDebugMDA::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="2e3a1-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="2e3a1-103">によって表されるマネージデバッグアシスタント (MDA) の名前を含む文字列を[取得します](icordebugmda-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="2e3a1-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e3a1-104">構文</span><span class="sxs-lookup"><span data-stu-id="2e3a1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e3a1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e3a1-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="2e3a1-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="2e3a1-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2e3a1-107">入出力名前の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2e3a1-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="2e3a1-108">入出力名前を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="2e3a1-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e3a1-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2e3a1-109">Remarks</span></span>  
 <span data-ttu-id="2e3a1-110">MDA 名は一意の値です。</span><span class="sxs-lookup"><span data-stu-id="2e3a1-110">MDA names are unique values.</span></span> <span data-ttu-id="2e3a1-111">この `GetName` メソッドは、XML ストリームを取得し、そのスキーマに基づいてストリームから名前を抽出する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="2e3a1-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e3a1-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="2e3a1-112">Requirements</span></span>  
 <span data-ttu-id="2e3a1-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e3a1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e3a1-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e3a1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e3a1-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e3a1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e3a1-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e3a1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e3a1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e3a1-117">See also</span></span>

- [<span data-ttu-id="2e3a1-118">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2e3a1-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="2e3a1-119">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="2e3a1-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
