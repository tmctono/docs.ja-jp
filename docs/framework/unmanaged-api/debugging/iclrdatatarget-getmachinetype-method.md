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
ms.openlocfilehash: 941d1b4057ef78a6235a0ba853e48a000f2087e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122884"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="6768b-102">ICLRDataTarget::GetMachineType メソッド</span><span class="sxs-lookup"><span data-stu-id="6768b-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="6768b-103">ターゲットプロセスが使用している命令セットの種類の識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6768b-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6768b-104">構文</span><span class="sxs-lookup"><span data-stu-id="6768b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6768b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6768b-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="6768b-106">入出力ターゲットプロセスが使用している命令セットを示す値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6768b-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="6768b-107">返される `machineType` は、IMAGE_FILE_MACHINE 定数の1つです。これは、Winnt.h ヘッダーファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="6768b-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6768b-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="6768b-108">Requirements</span></span>  
 <span data-ttu-id="6768b-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6768b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6768b-110">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="6768b-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6768b-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6768b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6768b-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6768b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6768b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6768b-113">See also</span></span>

- [<span data-ttu-id="6768b-114">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6768b-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
