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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56a34a8f185ce600f4792cf05c3e95623b70ad6c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776540"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="16bd3-102">ICLRMetaHostPolicy インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16bd3-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="16bd3-103">提供、 [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)メソッドで、ポリシーの条件に基づいて、共通言語ランタイム (CLR) インターフェイスへのポインターを返します、アセンブリ、バージョン、および構成ファイルを管理します。</span><span class="sxs-lookup"><span data-stu-id="16bd3-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="16bd3-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="16bd3-104">Methods</span></span>  
  
|<span data-ttu-id="16bd3-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="16bd3-105">Method</span></span>|<span data-ttu-id="16bd3-106">説明</span><span class="sxs-lookup"><span data-stu-id="16bd3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="16bd3-107">GetRequestedRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="16bd3-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="16bd3-108">推奨される CLR インターフェイスがポリシーの条件に基づいて、アセンブリ、バージョン、および構成ファイルの管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="16bd3-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16bd3-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="16bd3-109">Remarks</span></span>  
 <span data-ttu-id="16bd3-110">このインターフェイスへの参照を呼び出して取得することができます、 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)次のコードに示すように機能します。</span><span class="sxs-lookup"><span data-stu-id="16bd3-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="16bd3-111">このインターフェイスは、実際に読み込むか、CLR が推奨の CLR バージョンがインストールされるか読み込まれている使用可能なバージョンに基づく返しますだけをアクティブ化。</span><span class="sxs-lookup"><span data-stu-id="16bd3-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="16bd3-112">API をホストしている .NET Framework 4 は、特定のニーズを持つホストは意図しない低下を発生させずに基本的な機能を使用することがありますようにポリシーを統合します。</span><span class="sxs-lookup"><span data-stu-id="16bd3-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="16bd3-113">たとえば、メソッドが論理的にも必要ありませんが、特定の CLR にバインド MSCorEE.dll エクスポートの多くされます。</span><span class="sxs-lookup"><span data-stu-id="16bd3-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="16bd3-114">[METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)列挙体は、多数のホストに共通するバインディング ポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="16bd3-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16bd3-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="16bd3-115">Requirements</span></span>  
 <span data-ttu-id="16bd3-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16bd3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16bd3-117">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="16bd3-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="16bd3-118">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="16bd3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16bd3-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16bd3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16bd3-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="16bd3-120">See also</span></span>

- [<span data-ttu-id="16bd3-121">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16bd3-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="16bd3-122">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16bd3-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="16bd3-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="16bd3-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
