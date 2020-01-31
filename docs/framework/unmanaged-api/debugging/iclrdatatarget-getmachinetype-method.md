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
ms.openlocfilehash: 50ea9caf08b2ffb689760da95af4e5c3fdd77301
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793739"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="5a8a0-102">ICLRDataTarget::GetMachineType メソッド</span><span class="sxs-lookup"><span data-stu-id="5a8a0-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="5a8a0-103">ターゲットプロセスが使用している命令セットの種類の識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5a8a0-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a8a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a8a0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a8a0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a8a0-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="5a8a0-106">入出力ターゲットプロセスが使用している命令セットを示す値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5a8a0-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="5a8a0-107">返される `machineType` は、Winnt.h ヘッダーファイルで定義されている IMAGE_FILE_MACHINE 定数の1つです。</span><span class="sxs-lookup"><span data-stu-id="5a8a0-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a8a0-108">要件</span><span class="sxs-lookup"><span data-stu-id="5a8a0-108">Requirements</span></span>  
 <span data-ttu-id="5a8a0-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a8a0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a8a0-110">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="5a8a0-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5a8a0-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a8a0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a8a0-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a8a0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a8a0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a8a0-113">See also</span></span>

- [<span data-ttu-id="5a8a0-114">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a8a0-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
