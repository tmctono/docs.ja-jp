---
title: ICorRuntimeHost::CreateDomainSetup メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: aa1ce70311cd4ef0204c1c31efee8bd7b313c81d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762332"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="c4f33-102">ICorRuntimeHost::CreateDomainSetup メソッド</span><span class="sxs-lookup"><span data-stu-id="c4f33-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="c4f33-103">インスタンスへの IAppDomainSetup 型のインターフェイスポインターを取得し <xref:System.AppDomainSetup?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="c4f33-104">`IAppDomainSetup`アプリケーションドメインを作成する前に構成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="c4f33-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4f33-105">構文</span><span class="sxs-lookup"><span data-stu-id="c4f33-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4f33-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4f33-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="c4f33-107">入出力インスタンスへのインターフェイスポインター <xref:System.AppDomainSetup?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="c4f33-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="c4f33-108">このパラメーターはとして型指定さ `IUnknown` れるため、通常、呼び出し元は `QueryInterface` このポインターを呼び出して、型のインターフェイスポインターを取得する必要があり `IAppDomainSetup` ます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4f33-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="c4f33-109">Return Value</span></span>  
  
|<span data-ttu-id="c4f33-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c4f33-110">HRESULT</span></span>|<span data-ttu-id="c4f33-111">説明</span><span class="sxs-lookup"><span data-stu-id="c4f33-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4f33-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4f33-112">S_OK</span></span>|<span data-ttu-id="c4f33-113">操作に成功しました。</span><span class="sxs-lookup"><span data-stu-id="c4f33-113">The operation was successful.</span></span>|  
|<span data-ttu-id="c4f33-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c4f33-114">S_FALSE</span></span>|<span data-ttu-id="c4f33-115">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="c4f33-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="c4f33-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c4f33-116">E_FAIL</span></span>|<span data-ttu-id="c4f33-117">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c4f33-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="c4f33-118">メソッドが E_FAIL を返す場合、このプロセスでは共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c4f33-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="c4f33-119">後続のホスト Api への呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c4f33-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c4f33-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c4f33-121">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="c4f33-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4f33-122">解説</span><span class="sxs-lookup"><span data-stu-id="c4f33-122">Remarks</span></span>  
 <span data-ttu-id="c4f33-123">このメソッドから返されるポインターは、通常、パラメーターとして[Createdomainex](icorruntimehost-createdomainex-method.md)メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="c4f33-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4f33-124">要件</span><span class="sxs-lookup"><span data-stu-id="c4f33-124">Requirements</span></span>  
 <span data-ttu-id="c4f33-125">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4f33-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4f33-126">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c4f33-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4f33-127">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c4f33-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4f33-128">**.NET Framework バージョン:** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="c4f33-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f33-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4f33-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="c4f33-130">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c4f33-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
