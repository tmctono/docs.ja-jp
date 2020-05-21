---
title: ICorRuntimeHost::LocksHeldByLogicalThread メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
ms.openlocfilehash: 265ab5ae03b7b42c4f5f429df5d659d60e55f18e
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760720"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="a0c0c-102">ICorRuntimeHost::LocksHeldByLogicalThread メソッド</span><span class="sxs-lookup"><span data-stu-id="a0c0c-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="a0c0c-103">現在のスレッドが保持しているロックの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="a0c0c-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="a0c0c-104">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="a0c0c-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0c0c-105">構文</span><span class="sxs-lookup"><span data-stu-id="a0c0c-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0c0c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0c0c-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="a0c0c-107">入出力現在のスレッドが保持しているロックの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a0c0c-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0c0c-108">要件</span><span class="sxs-lookup"><span data-stu-id="a0c0c-108">Requirements</span></span>  
 <span data-ttu-id="a0c0c-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0c0c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0c0c-110">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a0c0c-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0c0c-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a0c0c-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0c0c-112">**.NET Framework のバージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="a0c0c-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c0c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0c0c-113">See also</span></span>

- [<span data-ttu-id="a0c0c-114">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a0c0c-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
