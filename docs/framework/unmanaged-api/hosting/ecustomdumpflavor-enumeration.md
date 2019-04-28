---
title: ECustomDumpFlavor 列挙型
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1e69d9cbf39049e82803d2f7bc795cc9fd0b368
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796007"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="686b1-102">ECustomDumpFlavor 列挙型</span><span class="sxs-lookup"><span data-stu-id="686b1-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="686b1-103">エラーを報告するときにカスタム ヒープのサブセットに含める項目のダンプを示す値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="686b1-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="686b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="686b1-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="686b1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="686b1-105">Members</span></span>  
  
|<span data-ttu-id="686b1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="686b1-106">Member</span></span>|<span data-ttu-id="686b1-107">説明</span><span class="sxs-lookup"><span data-stu-id="686b1-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="686b1-108">カスタム ヒープ ダンプがミニダンプとして起動し、いずれかで指定された追加のデータを含めることを指定します[CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)インスタンスが同じメソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="686b1-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="686b1-109">カスタム ヒープ ダンプが動的に割り当てられていないすべての実行時の状態データを収集する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="686b1-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="686b1-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="686b1-110">Remarks</span></span>  
 <span data-ttu-id="686b1-111">型のパラメーター`ECustomDumpFlavor`に渡される、 [iclrerrorreportingmanager::begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="686b1-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="686b1-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="686b1-112">Requirements</span></span>  
 <span data-ttu-id="686b1-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="686b1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="686b1-114">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="686b1-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="686b1-115">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="686b1-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="686b1-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="686b1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="686b1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="686b1-117">See also</span></span>

- [<span data-ttu-id="686b1-118">ECustomDumpItemKind 列挙型</span><span class="sxs-lookup"><span data-stu-id="686b1-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="686b1-119">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="686b1-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="686b1-120">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="686b1-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
