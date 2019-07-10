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
ms.openlocfilehash: 1201ac0dca9cbd48c24b2621eba079ae672fd310
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737843"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="8ad59-102">ICorDebugAppDomain::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="8ad59-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="8ad59-103">共通言語ランタイム (CLR) のアプリケーション ドメインにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="8ad59-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ad59-104">構文</span><span class="sxs-lookup"><span data-stu-id="8ad59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ad59-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ad59-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="8ad59-106">[out]CLR のアプリケーション ドメインを表す ICorDebugValue インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8ad59-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ad59-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="8ad59-107">Return Value</span></span>  
 <span data-ttu-id="8ad59-108">マネージ場合<xref:System.AppDomain?displayProperty=nameWithType>このアプリケーション ドメインのオブジェクトが作成されていないメソッドを返します`S_FALSE`配置`NULL`で`*ppObject`します。</span><span class="sxs-lookup"><span data-stu-id="8ad59-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ad59-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="8ad59-109">Remarks</span></span>  
 <span data-ttu-id="8ad59-110">マネージ プロセス内の各アプリケーション ドメインがあります<xref:System.AppDomain?displayProperty=nameWithType>それを表す、ランタイム内のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8ad59-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="8ad59-111">この関数は、この管理に対応する ICorDebugValue インターフェイス オブジェクトを取得します<xref:System.AppDomain?displayProperty=nameWithType>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8ad59-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ad59-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="8ad59-112">Requirements</span></span>  
 <span data-ttu-id="8ad59-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ad59-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ad59-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ad59-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ad59-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ad59-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ad59-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ad59-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
