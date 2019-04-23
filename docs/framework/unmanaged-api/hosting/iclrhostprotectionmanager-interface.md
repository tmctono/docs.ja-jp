---
title: ICLRHostProtectionManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd096344c987d8901f0baab86e370abbb03528e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177776"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="15375-102">ICLRHostProtectionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15375-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="15375-103">特定のマネージ クラス、メソッド、プロパティ、およびフィールドを部分的に信頼されたコードでの実行をブロックするホストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="15375-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15375-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="15375-104">Methods</span></span>  
  
|<span data-ttu-id="15375-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="15375-105">Method</span></span>|<span data-ttu-id="15375-106">説明</span><span class="sxs-lookup"><span data-stu-id="15375-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15375-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="15375-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="15375-108">致命的な共通言語ランタイム (CLR) のエラーが発生する特定のまれな競合条件が発生しないことの保証を提供します。</span><span class="sxs-lookup"><span data-stu-id="15375-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="15375-109">SetProtectedCategories メソッド</span><span class="sxs-lookup"><span data-stu-id="15375-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="15375-110">マネージ型と部分的に信頼されたコードで実行されているを禁止するメンバーのカテゴリを指定します。</span><span class="sxs-lookup"><span data-stu-id="15375-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15375-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="15375-111">Requirements</span></span>  
 <span data-ttu-id="15375-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15375-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15375-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15375-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15375-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="15375-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15375-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15375-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15375-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="15375-116">See also</span></span>

- [<span data-ttu-id="15375-117">EApiCategories 列挙型</span><span class="sxs-lookup"><span data-stu-id="15375-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="15375-118">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15375-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
