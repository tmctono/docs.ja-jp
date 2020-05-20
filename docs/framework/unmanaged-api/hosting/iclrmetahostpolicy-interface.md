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
ms.openlocfilehash: 79b62a5e2aad9cfcd14ba40c1abf0342bfe57a4b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703531"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="feeb3-102">ICLRMetaHostPolicy インターフェイス</span><span class="sxs-lookup"><span data-stu-id="feeb3-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="feeb3-103">[Getrequestedruntime](iclrmetahostpolicy-getrequestedruntime-method.md)メソッドを提供します。このメソッドは、ポリシー条件、マネージアセンブリ、バージョン、および構成ファイルに基づいて共通言語ランタイム (CLR) インターフェイスへのポインターを返します。</span><span class="sxs-lookup"><span data-stu-id="feeb3-103">Provides the [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="feeb3-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="feeb3-104">Methods</span></span>  
  
|<span data-ttu-id="feeb3-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="feeb3-105">Method</span></span>|<span data-ttu-id="feeb3-106">説明</span><span class="sxs-lookup"><span data-stu-id="feeb3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="feeb3-107">GetRequestedRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="feeb3-107">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="feeb3-108">ポリシー条件、マネージアセンブリ、バージョン、および構成ファイルに基づいて、優先する CLR インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="feeb3-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="feeb3-109">解説</span><span class="sxs-lookup"><span data-stu-id="feeb3-109">Remarks</span></span>  
 <span data-ttu-id="feeb3-110">このインターフェイスへの参照を取得するには、次のコードに示すように[Clrcreateinstance](clrcreateinstance-function.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="feeb3-110">You can get a reference to this interface by calling the [CLRCreateInstance](clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> <span data-ttu-id="feeb3-111">このインターフェイスは、実際には CLR の読み込みもアクティブ化も行いませんが、インストールまたは読み込まれている使用可能なバージョンに基づいて、単純に優先 CLR バージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="feeb3-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="feeb3-112">.NET Framework 4 ホスト API はポリシーを統合して、特定のニーズを持つホストが、意図しない罰則を伴わずに基本的な機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="feeb3-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="feeb3-113">たとえば、多くの Mscoree.dll のエクスポートは特定の CLR にバインドされますが、メソッドでは論理的に要求されない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="feeb3-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="feeb3-114">[METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md)列挙体は、ほとんどのホストに共通するバインドポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="feeb3-114">The [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feeb3-115">要件</span><span class="sxs-lookup"><span data-stu-id="feeb3-115">Requirements</span></span>  
 <span data-ttu-id="feeb3-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feeb3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feeb3-117">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="feeb3-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="feeb3-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="feeb3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="feeb3-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="feeb3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feeb3-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="feeb3-120">See also</span></span>

- [<span data-ttu-id="feeb3-121">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="feeb3-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="feeb3-122">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="feeb3-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="feeb3-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="feeb3-123">Hosting</span></span>](index.md)
