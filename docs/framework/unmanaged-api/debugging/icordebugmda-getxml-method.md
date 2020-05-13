---
title: ICorDebugMDA::GetXML メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
ms.openlocfilehash: 219aa27296dffa525bf3e2b836825437a8ce77b0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207655"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="49ed6-102">ICorDebugMDA::GetXML メソッド</span><span class="sxs-lookup"><span data-stu-id="49ed6-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="49ed6-103">[によって](icordebugmda-interface.md)表されるマネージデバッグアシスタント (MDA) に関連付けられた完全な XML ストリームを取得します。</span><span class="sxs-lookup"><span data-stu-id="49ed6-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49ed6-104">構文</span><span class="sxs-lookup"><span data-stu-id="49ed6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49ed6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="49ed6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="49ed6-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="49ed6-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="49ed6-107">入出力XML ストリームの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="49ed6-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="49ed6-108">入出力XML ストリームを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="49ed6-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="49ed6-109">配列が空である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="49ed6-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49ed6-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="49ed6-110">Remarks</span></span>  
 <span data-ttu-id="49ed6-111">メソッドは、 `GetXML` 関連付けられている XML ストリームのサイズによっては、パフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="49ed6-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49ed6-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="49ed6-112">Requirements</span></span>  
 <span data-ttu-id="49ed6-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ed6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49ed6-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49ed6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49ed6-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49ed6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49ed6-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49ed6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49ed6-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="49ed6-117">See also</span></span>

- [<span data-ttu-id="49ed6-118">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="49ed6-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="49ed6-119">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="49ed6-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
