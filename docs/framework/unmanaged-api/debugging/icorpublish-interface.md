---
title: ICorPublish インターフェイス
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: c4a24d879ebd9e8813ea0ac4597818569f4ae6fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790723"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="3998b-102">ICorPublish インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3998b-102">ICorPublish Interface</span></span>
<span data-ttu-id="3998b-103">プロセスに関する情報、およびそれらのプロセス内のアプリケーションドメインに関する情報を公開するための一般的なインターフェイスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="3998b-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3998b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3998b-104">Methods</span></span>  
  
|<span data-ttu-id="3998b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3998b-105">Method</span></span>|<span data-ttu-id="3998b-106">説明</span><span class="sxs-lookup"><span data-stu-id="3998b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3998b-107">EnumProcesses メソッド</span><span class="sxs-lookup"><span data-stu-id="3998b-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="3998b-108">このコンピューター上で実行されているマネージプロセスを含む[ICorPublishProcessEnum](icorpublishprocessenum-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="3998b-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="3998b-109">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="3998b-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="3998b-110">指定した識別子を持つプロセスを表す[ICorPublishProcess](icorpublishprocess-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="3998b-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3998b-111">要件</span><span class="sxs-lookup"><span data-stu-id="3998b-111">Requirements</span></span>  
 <span data-ttu-id="3998b-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3998b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3998b-113">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="3998b-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3998b-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3998b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3998b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3998b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3998b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3998b-116">See also</span></span>

- [<span data-ttu-id="3998b-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3998b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3998b-118">CorpubPublish コクラス</span><span class="sxs-lookup"><span data-stu-id="3998b-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
