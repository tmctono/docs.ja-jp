---
title: ICorDebugAssembly::GetName メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3077e0494816a083d97839d66d06b18130e5dac8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645579"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="6d824-102">ICorDebugAssembly::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="6d824-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="6d824-103">アセンブリの名前を取得しますこの`ICorDebugAssembly`インスタンスが表す。</span><span class="sxs-lookup"><span data-stu-id="6d824-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d824-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d824-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d824-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d824-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6d824-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="6d824-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6d824-107">[out]名前の実際の長さを指定する整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6d824-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="6d824-108">[out]名前を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="6d824-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d824-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6d824-109">Remarks</span></span>  
 <span data-ttu-id="6d824-110">`GetName`メソッドは、アセンブリの完全なパスとファイル名を返します。</span><span class="sxs-lookup"><span data-stu-id="6d824-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d824-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6d824-111">Requirements</span></span>  
 <span data-ttu-id="6d824-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d824-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d824-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d824-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d824-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d824-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d824-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d824-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
