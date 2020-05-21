---
title: ICorRuntimeHost::CloseEnum メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
ms.openlocfilehash: a5a86df3ac1f50ca624490ad80a6fed903433436
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762371"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="76ce3-102">ICorRuntimeHost::CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="76ce3-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="76ce3-103">ドメイン列挙子をドメインリストの先頭にリセットします。</span><span class="sxs-lookup"><span data-stu-id="76ce3-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ce3-104">構文</span><span class="sxs-lookup"><span data-stu-id="76ce3-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76ce3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="76ce3-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="76ce3-106">からリセットする列挙子。</span><span class="sxs-lookup"><span data-stu-id="76ce3-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76ce3-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="76ce3-107">Return Value</span></span>  
  
|<span data-ttu-id="76ce3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76ce3-108">HRESULT</span></span>|<span data-ttu-id="76ce3-109">説明</span><span class="sxs-lookup"><span data-stu-id="76ce3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76ce3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="76ce3-110">S_OK</span></span>|<span data-ttu-id="76ce3-111">操作に成功しました。</span><span class="sxs-lookup"><span data-stu-id="76ce3-111">The operation was successful.</span></span>|  
|<span data-ttu-id="76ce3-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="76ce3-112">S_FALSE</span></span>|<span data-ttu-id="76ce3-113">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="76ce3-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="76ce3-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="76ce3-114">E_FAIL</span></span>|<span data-ttu-id="76ce3-115">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="76ce3-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="76ce3-116">メソッドが E_FAIL を返す場合、このプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="76ce3-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="76ce3-117">後続のホスト Api への呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="76ce3-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="76ce3-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="76ce3-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="76ce3-119">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="76ce3-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76ce3-120">要件</span><span class="sxs-lookup"><span data-stu-id="76ce3-120">Requirements</span></span>  
 <span data-ttu-id="76ce3-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76ce3-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ce3-122">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="76ce3-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76ce3-123">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="76ce3-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76ce3-124">**.NET Framework のバージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="76ce3-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ce3-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="76ce3-125">See also</span></span>

- [<span data-ttu-id="76ce3-126">CorBindToRuntimeEx 関数</span><span class="sxs-lookup"><span data-stu-id="76ce3-126">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="76ce3-127">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76ce3-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
