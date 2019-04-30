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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989509"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="de255-102">ICorDebugAppDomainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de255-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="de255-103">提供、 `Next` 、指定した数を返すメソッド`ICorDebugAppDomainEnum`列挙体の次の場所から始まる値。</span><span class="sxs-lookup"><span data-stu-id="de255-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="de255-104">このインターフェイスは、"ICorDebugEnum"のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="de255-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de255-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="de255-105">Methods</span></span>  
  
|<span data-ttu-id="de255-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="de255-106">Method</span></span>|<span data-ttu-id="de255-107">説明</span><span class="sxs-lookup"><span data-stu-id="de255-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de255-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="de255-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="de255-109">現在のカーソル位置から、コレクションから指定されたアプリケーション ドメイン数を取得します。</span><span class="sxs-lookup"><span data-stu-id="de255-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de255-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="de255-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de255-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="de255-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de255-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="de255-112">Requirements</span></span>  
 <span data-ttu-id="de255-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de255-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de255-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de255-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de255-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de255-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de255-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de255-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de255-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="de255-117">See also</span></span>

- [<span data-ttu-id="de255-118">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de255-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="de255-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de255-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
