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
ms.openlocfilehash: daf5319f5d57f44cb20ce9f28d3c7b84c7015ff6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894915"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="8db40-102">ICorDebugAssembly::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="8db40-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="8db40-103">この`ICorDebugAssembly`インスタンスが表すアセンブリの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="8db40-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db40-104">構文</span><span class="sxs-lookup"><span data-stu-id="8db40-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8db40-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8db40-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="8db40-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="8db40-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8db40-107">入出力名前の実際の長さを指定する整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8db40-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="8db40-108">入出力名前を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="8db40-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8db40-109">解説</span><span class="sxs-lookup"><span data-stu-id="8db40-109">Remarks</span></span>  
 <span data-ttu-id="8db40-110">メソッド`GetName`は、アセンブリの完全なパスとファイル名を返します。</span><span class="sxs-lookup"><span data-stu-id="8db40-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8db40-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8db40-111">Requirements</span></span>  
 <span data-ttu-id="8db40-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8db40-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8db40-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8db40-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8db40-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8db40-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8db40-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8db40-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
