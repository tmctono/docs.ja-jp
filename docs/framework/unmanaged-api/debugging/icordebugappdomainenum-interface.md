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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da1fc949109455cf50767191a99a8a727116f77c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155195"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="025bb-102">ICorDebugAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="025bb-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="025bb-103">提供、 `Next` 、指定した数を返すメソッド`ICorDebugAppDomainEnum`列挙体の次の場所から始まる値。</span><span class="sxs-lookup"><span data-stu-id="025bb-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="025bb-104">このインターフェイスは、"ICorDebugEnum"のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="025bb-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="025bb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="025bb-105">Methods</span></span>  
  
|<span data-ttu-id="025bb-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="025bb-106">Method</span></span>|<span data-ttu-id="025bb-107">説明</span><span class="sxs-lookup"><span data-stu-id="025bb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="025bb-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="025bb-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="025bb-109">現在のカーソル位置から、コレクションから指定されたアプリケーション ドメイン数を取得します。</span><span class="sxs-lookup"><span data-stu-id="025bb-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="025bb-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="025bb-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="025bb-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="025bb-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="025bb-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="025bb-112">Requirements</span></span>  
 <span data-ttu-id="025bb-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="025bb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="025bb-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="025bb-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="025bb-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="025bb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="025bb-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="025bb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="025bb-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="025bb-117">See also</span></span>

- [<span data-ttu-id="025bb-118">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="025bb-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="025bb-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="025bb-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
