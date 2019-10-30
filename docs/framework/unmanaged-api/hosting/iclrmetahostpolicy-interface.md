---
title: ICLRMetaHostPolicy インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
ms.openlocfilehash: 277c13895374116eb67f6515f45df638f61b0453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140858"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="f1bcc-102">ICLRMetaHostPolicy インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1bcc-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="f1bcc-103">[Getrequestedruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)メソッドを提供します。このメソッドは、ポリシー条件、マネージアセンブリ、バージョン、および構成ファイルに基づいて共通言語ランタイム (CLR) インターフェイスへのポインターを返します。</span><span class="sxs-lookup"><span data-stu-id="f1bcc-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1bcc-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f1bcc-104">Methods</span></span>  
  
|<span data-ttu-id="f1bcc-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f1bcc-105">Method</span></span>|<span data-ttu-id="f1bcc-106">説明</span><span class="sxs-lookup"><span data-stu-id="f1bcc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1bcc-107">GetRequestedRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="f1bcc-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="f1bcc-108">ポリシー条件、マネージアセンブリ、バージョン、および構成ファイルに基づいて、優先する CLR インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f1bcc-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1bcc-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1bcc-109">Remarks</span></span>  
 <span data-ttu-id="f1bcc-110">このインターフェイスへの参照を取得するには、次のコードに示すように[Clrcreateinstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f1bcc-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> <span data-ttu-id="f1bcc-111">このインターフェイスは、実際には CLR の読み込みもアクティブ化も行いませんが、インストールまたは読み込まれている使用可能なバージョンに基づいて、単純に優先 CLR バージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="f1bcc-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="f1bcc-112">.NET Framework 4 ホスト API はポリシーを統合して、特定のニーズを持つホストが、意図しない罰則を伴わずに基本的な機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f1bcc-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="f1bcc-113">たとえば、多くの Mscoree.dll のエクスポートは特定の CLR にバインドされますが、メソッドでは論理的に要求されない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f1bcc-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="f1bcc-114">[METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)列挙体は、ほとんどのホストに共通のバインドポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="f1bcc-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1bcc-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="f1bcc-115">Requirements</span></span>  
 <span data-ttu-id="f1bcc-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1bcc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1bcc-117">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="f1bcc-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f1bcc-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f1bcc-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1bcc-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1bcc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1bcc-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1bcc-120">See also</span></span>

- [<span data-ttu-id="f1bcc-121">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1bcc-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="f1bcc-122">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1bcc-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="f1bcc-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="f1bcc-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
