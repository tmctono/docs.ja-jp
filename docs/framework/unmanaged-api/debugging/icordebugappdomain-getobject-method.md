---
title: ICorDebugAppDomain::GetObject メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ca9792df69f859e20f1d9e40754d1cec138945d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480027"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="e884e-102">ICorDebugAppDomain::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="e884e-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="e884e-103">共通言語ランタイム (CLR) のアプリケーション ドメインにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e884e-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e884e-104">構文</span><span class="sxs-lookup"><span data-stu-id="e884e-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e884e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e884e-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="e884e-106">[out]CLR のアプリケーション ドメインを表す ICorDebugValue インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e884e-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e884e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="e884e-107">Return Value</span></span>  
 <span data-ttu-id="e884e-108">マネージ場合<xref:System.AppDomain?displayProperty=nameWithType>このアプリケーション ドメインのオブジェクトが作成されていないメソッドを返します`S_FALSE`配置`NULL`で`*ppObject`します。</span><span class="sxs-lookup"><span data-stu-id="e884e-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e884e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e884e-109">Remarks</span></span>  
 <span data-ttu-id="e884e-110">マネージ プロセス内の各アプリケーション ドメインがあります<xref:System.AppDomain?displayProperty=nameWithType>それを表す、ランタイム内のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e884e-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="e884e-111">この関数は、この管理に対応する ICorDebugValue インターフェイス オブジェクトを取得します<xref:System.AppDomain?displayProperty=nameWithType>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e884e-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e884e-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="e884e-112">Requirements</span></span>  
 <span data-ttu-id="e884e-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e884e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e884e-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e884e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e884e-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e884e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e884e-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e884e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
