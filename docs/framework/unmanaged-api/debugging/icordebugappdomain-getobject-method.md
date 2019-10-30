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
ms.openlocfilehash: f2c881603cfa0e4b3d2dc8d1e996631b51d1e850
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134715"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="30037-102">ICorDebugAppDomain::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="30037-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="30037-103">共通言語ランタイム (CLR) アプリケーションドメインへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="30037-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30037-104">構文</span><span class="sxs-lookup"><span data-stu-id="30037-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30037-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="30037-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="30037-106">入出力CLR アプリケーションドメインを表す ICorDebugValue インターフェイスオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="30037-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30037-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="30037-107">Return Value</span></span>  
 <span data-ttu-id="30037-108">このアプリケーションドメインに対してマネージ <xref:System.AppDomain?displayProperty=nameWithType> オブジェクトが構築されていない場合、メソッドは `S_FALSE` を返し、`NULL` を `*ppObject`に配置します。</span><span class="sxs-lookup"><span data-stu-id="30037-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30037-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="30037-109">Remarks</span></span>  
 <span data-ttu-id="30037-110">プロセス内の各アプリケーションドメインは、それを表すランタイムにマネージ <xref:System.AppDomain?displayProperty=nameWithType> オブジェクトを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="30037-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="30037-111">この関数は、このマネージ <xref:System.AppDomain?displayProperty=nameWithType> オブジェクトに対応する ICorDebugValue インターフェイスオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="30037-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30037-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="30037-112">Requirements</span></span>  
 <span data-ttu-id="30037-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30037-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30037-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30037-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30037-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30037-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30037-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30037-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
