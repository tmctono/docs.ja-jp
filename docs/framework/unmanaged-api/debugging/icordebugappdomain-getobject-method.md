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
ms.openlocfilehash: a21f3b36e418bbde5dcb90f25a39dae03fde77c9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895207"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="2fc6e-102">ICorDebugAppDomain::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="2fc6e-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="2fc6e-103">共通言語ランタイム (CLR) アプリケーションドメインへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2fc6e-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fc6e-104">構文</span><span class="sxs-lookup"><span data-stu-id="2fc6e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fc6e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fc6e-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="2fc6e-106">入出力CLR アプリケーションドメインを表す ICorDebugValue インターフェイスオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2fc6e-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fc6e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2fc6e-107">Return Value</span></span>  
 <span data-ttu-id="2fc6e-108">このアプリケーションドメイン<xref:System.AppDomain?displayProperty=nameWithType>に対してマネージオブジェクトが構築されていない`S_FALSE`場合、 `NULL`メソッド`*ppObject`はを返し、をに配置します。</span><span class="sxs-lookup"><span data-stu-id="2fc6e-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fc6e-109">解説</span><span class="sxs-lookup"><span data-stu-id="2fc6e-109">Remarks</span></span>  
 <span data-ttu-id="2fc6e-110">プロセス内の各アプリケーションドメインは、それを<xref:System.AppDomain?displayProperty=nameWithType>表すランタイムにマネージオブジェクトを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="2fc6e-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="2fc6e-111">この関数は、このマネージ<xref:System.AppDomain?displayProperty=nameWithType>オブジェクトに対応する ICorDebugValue インターフェイスオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="2fc6e-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fc6e-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="2fc6e-112">Requirements</span></span>  
 <span data-ttu-id="2fc6e-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc6e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fc6e-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fc6e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fc6e-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fc6e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fc6e-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fc6e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
