---
title: ICorDebugAppDomainEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: 6cc3ec1c802c28b74248380aa7f686e675a92f1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088837"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="6cf79-102">ICorDebugAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6cf79-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="6cf79-103">`Next` メソッドを提供します。このメソッドは、列挙体の次の位置から始まる指定された数の `ICorDebugAppDomainEnum` 値を返します。</span><span class="sxs-lookup"><span data-stu-id="6cf79-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="6cf79-104">このインターフェイスは、"ICorDebugEnum" のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="6cf79-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6cf79-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6cf79-105">Methods</span></span>  
  
|<span data-ttu-id="6cf79-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="6cf79-106">Method</span></span>|<span data-ttu-id="6cf79-107">説明</span><span class="sxs-lookup"><span data-stu-id="6cf79-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6cf79-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="6cf79-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="6cf79-109">現在のカーソル位置から開始して、指定した数のアプリケーションドメインをコレクションから取得します。</span><span class="sxs-lookup"><span data-stu-id="6cf79-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cf79-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="6cf79-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6cf79-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6cf79-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cf79-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="6cf79-112">Requirements</span></span>  
 <span data-ttu-id="6cf79-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cf79-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cf79-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6cf79-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6cf79-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cf79-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cf79-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cf79-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf79-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cf79-117">See also</span></span>

- [<span data-ttu-id="6cf79-118">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6cf79-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="6cf79-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6cf79-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
