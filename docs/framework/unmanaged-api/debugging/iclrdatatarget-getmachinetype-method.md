---
title: ICLRDataTarget::GetMachineType メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5727142f55e143cf144dae842f95a36effb33c68
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482237"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="2ffce-102">ICLRDataTarget::GetMachineType メソッド</span><span class="sxs-lookup"><span data-stu-id="2ffce-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="2ffce-103">ターゲット プロセスを使用している命令セットの種類の識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="2ffce-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ffce-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ffce-104">Syntax</span></span>  
  
```  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ffce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ffce-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="2ffce-106">[out]命令セットをターゲット プロセスを示す値を指すポインターが使用されています。</span><span class="sxs-lookup"><span data-stu-id="2ffce-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="2ffce-107">返された`machineType`WinNT.h ヘッダー ファイルで定義されている IMAGE_FILE_MACHINE 定数の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="2ffce-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ffce-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="2ffce-108">Requirements</span></span>  
 <span data-ttu-id="2ffce-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ffce-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ffce-110">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="2ffce-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2ffce-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ffce-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ffce-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ffce-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ffce-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ffce-113">See also</span></span>
- [<span data-ttu-id="2ffce-114">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ffce-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
