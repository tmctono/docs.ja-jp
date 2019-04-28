---
title: OLE DB スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771996"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="e251e-102">OLE DB スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="e251e-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="e251e-103">ここでは、Microsoft SQL Server、Oracle、および Microsoft Jet 用の各 OLE DB プロバイダーでのスキーマ コレクションのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e251e-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="e251e-104">Microsoft SQL Server OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="e251e-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="e251e-105">Microsoft SQL Server OLE DB Driver は、共通のスキーマ コレクションに加えて次の特定のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e251e-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="e251e-106">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e251e-106">Tables</span></span>  
  
- <span data-ttu-id="e251e-107">列</span><span class="sxs-lookup"><span data-stu-id="e251e-107">Columns</span></span>  
  
- <span data-ttu-id="e251e-108">手順</span><span class="sxs-lookup"><span data-stu-id="e251e-108">Procedures</span></span>  
  
- <span data-ttu-id="e251e-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e251e-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="e251e-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="e251e-110">Catalog</span></span>  
  
- <span data-ttu-id="e251e-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="e251e-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e251e-112">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e251e-112">Tables</span></span>  
  
|<span data-ttu-id="e251e-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-113">ColumnName</span></span>|<span data-ttu-id="e251e-114">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-115">TABLE_CATALOG</span></span>|<span data-ttu-id="e251e-116">String</span><span class="sxs-lookup"><span data-stu-id="e251e-116">String</span></span>|  
|<span data-ttu-id="e251e-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="e251e-118">String</span><span class="sxs-lookup"><span data-stu-id="e251e-118">String</span></span>|  
|<span data-ttu-id="e251e-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-119">TABLE_NAME</span></span>|<span data-ttu-id="e251e-120">String</span><span class="sxs-lookup"><span data-stu-id="e251e-120">String</span></span>|  
|<span data-ttu-id="e251e-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-121">TABLE_TYPE</span></span>|<span data-ttu-id="e251e-122">String</span><span class="sxs-lookup"><span data-stu-id="e251e-122">String</span></span>|  
|<span data-ttu-id="e251e-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-123">TABLE_GUID</span></span>|<span data-ttu-id="e251e-124">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-124">Guid</span></span>|  
|<span data-ttu-id="e251e-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-125">DESCRIPTION</span></span>|<span data-ttu-id="e251e-126">String</span><span class="sxs-lookup"><span data-stu-id="e251e-126">String</span></span>|  
|<span data-ttu-id="e251e-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e251e-127">TABLE_PROPID</span></span>|<span data-ttu-id="e251e-128">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-128">Int64</span></span>|  
|<span data-ttu-id="e251e-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e251e-129">DATE_CREATED</span></span>|<span data-ttu-id="e251e-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-130">DateTime</span></span>|  
|<span data-ttu-id="e251e-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e251e-131">DATE_MODIFIED</span></span>|<span data-ttu-id="e251e-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e251e-133">列</span><span class="sxs-lookup"><span data-stu-id="e251e-133">Columns</span></span>  
  
|<span data-ttu-id="e251e-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-134">ColumnName</span></span>|<span data-ttu-id="e251e-135">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-136">TABLE_CATALOG</span></span>|<span data-ttu-id="e251e-137">String</span><span class="sxs-lookup"><span data-stu-id="e251e-137">String</span></span>|  
|<span data-ttu-id="e251e-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="e251e-139">String</span><span class="sxs-lookup"><span data-stu-id="e251e-139">String</span></span>|  
|<span data-ttu-id="e251e-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-140">TABLE_NAME</span></span>|<span data-ttu-id="e251e-141">String</span><span class="sxs-lookup"><span data-stu-id="e251e-141">String</span></span>|  
|<span data-ttu-id="e251e-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-142">COLUMN_NAME</span></span>|<span data-ttu-id="e251e-143">String</span><span class="sxs-lookup"><span data-stu-id="e251e-143">String</span></span>|  
|<span data-ttu-id="e251e-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-144">COLUMN_GUID</span></span>|<span data-ttu-id="e251e-145">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-145">Guid</span></span>|  
|<span data-ttu-id="e251e-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e251e-146">COLUMN_PROPID</span></span>|<span data-ttu-id="e251e-147">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-147">Int64</span></span>|  
|<span data-ttu-id="e251e-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e251e-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="e251e-149">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-149">Int64</span></span>|  
|<span data-ttu-id="e251e-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e251e-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e251e-151">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-151">Boolean</span></span>|  
|<span data-ttu-id="e251e-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e251e-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e251e-153">String</span><span class="sxs-lookup"><span data-stu-id="e251e-153">String</span></span>|  
|<span data-ttu-id="e251e-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e251e-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="e251e-155">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-155">Int64</span></span>|  
|<span data-ttu-id="e251e-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e251e-156">IS_NULLABLE</span></span>|<span data-ttu-id="e251e-157">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-157">Boolean</span></span>|  
|<span data-ttu-id="e251e-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-158">DATA_TYPE</span></span>|<span data-ttu-id="e251e-159">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-159">Int32</span></span>|  
|<span data-ttu-id="e251e-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-160">TYPE_GUID</span></span>|<span data-ttu-id="e251e-161">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-161">Guid</span></span>|  
|<span data-ttu-id="e251e-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e251e-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e251e-163">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-163">Int64</span></span>|  
|<span data-ttu-id="e251e-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e251e-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e251e-165">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-165">Int64</span></span>|  
|<span data-ttu-id="e251e-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e251e-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e251e-167">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-167">Int32</span></span>|  
|<span data-ttu-id="e251e-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e251e-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="e251e-169">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-169">Int16</span></span>|  
|<span data-ttu-id="e251e-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e251e-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="e251e-171">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-171">Int64</span></span>|  
|<span data-ttu-id="e251e-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e251e-173">String</span><span class="sxs-lookup"><span data-stu-id="e251e-173">String</span></span>|  
|<span data-ttu-id="e251e-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e251e-175">String</span><span class="sxs-lookup"><span data-stu-id="e251e-175">String</span></span>|  
|<span data-ttu-id="e251e-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e251e-177">String</span><span class="sxs-lookup"><span data-stu-id="e251e-177">String</span></span>|  
|<span data-ttu-id="e251e-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="e251e-179">String</span><span class="sxs-lookup"><span data-stu-id="e251e-179">String</span></span>|  
|<span data-ttu-id="e251e-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e251e-181">String</span><span class="sxs-lookup"><span data-stu-id="e251e-181">String</span></span>|  
|<span data-ttu-id="e251e-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-182">COLLATION_NAME</span></span>|<span data-ttu-id="e251e-183">String</span><span class="sxs-lookup"><span data-stu-id="e251e-183">String</span></span>|  
|<span data-ttu-id="e251e-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e251e-185">String</span><span class="sxs-lookup"><span data-stu-id="e251e-185">String</span></span>|  
|<span data-ttu-id="e251e-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e251e-187">String</span><span class="sxs-lookup"><span data-stu-id="e251e-187">String</span></span>|  
|<span data-ttu-id="e251e-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-188">DOMAIN_NAME</span></span>|<span data-ttu-id="e251e-189">String</span><span class="sxs-lookup"><span data-stu-id="e251e-189">String</span></span>|  
|<span data-ttu-id="e251e-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-190">DESCRIPTION</span></span>|<span data-ttu-id="e251e-191">String</span><span class="sxs-lookup"><span data-stu-id="e251e-191">String</span></span>|  
|<span data-ttu-id="e251e-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="e251e-192">COLUMN_LCID</span></span>|<span data-ttu-id="e251e-193">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-193">Int32</span></span>|  
|<span data-ttu-id="e251e-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="e251e-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="e251e-195">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-195">Int32</span></span>|  
|<span data-ttu-id="e251e-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="e251e-196">COLUMN_SORTID</span></span>|<span data-ttu-id="e251e-197">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-197">Int32</span></span>|  
|<span data-ttu-id="e251e-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="e251e-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="e251e-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="e251e-199">Byte[]</span></span>|  
|<span data-ttu-id="e251e-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="e251e-200">IS_COMPUTED</span></span>|<span data-ttu-id="e251e-201">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e251e-202">手順</span><span class="sxs-lookup"><span data-stu-id="e251e-202">Procedures</span></span>  
  
|<span data-ttu-id="e251e-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-203">ColumnName</span></span>|<span data-ttu-id="e251e-204">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e251e-206">String</span><span class="sxs-lookup"><span data-stu-id="e251e-206">String</span></span>|  
|<span data-ttu-id="e251e-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e251e-208">String</span><span class="sxs-lookup"><span data-stu-id="e251e-208">String</span></span>|  
|<span data-ttu-id="e251e-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="e251e-210">String</span><span class="sxs-lookup"><span data-stu-id="e251e-210">String</span></span>|  
|<span data-ttu-id="e251e-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e251e-212">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-212">Int16</span></span>|  
|<span data-ttu-id="e251e-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e251e-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e251e-214">String</span><span class="sxs-lookup"><span data-stu-id="e251e-214">String</span></span>|  
|<span data-ttu-id="e251e-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-215">DESCRIPTION</span></span>|<span data-ttu-id="e251e-216">String</span><span class="sxs-lookup"><span data-stu-id="e251e-216">String</span></span>|  
|<span data-ttu-id="e251e-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e251e-217">DATE_CREATED</span></span>|<span data-ttu-id="e251e-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-218">DateTime</span></span>|  
|<span data-ttu-id="e251e-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e251e-219">DATE_MODIFIED</span></span>|<span data-ttu-id="e251e-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="e251e-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e251e-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="e251e-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-222">ColumnName</span></span>|<span data-ttu-id="e251e-223">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e251e-225">String</span><span class="sxs-lookup"><span data-stu-id="e251e-225">String</span></span>|  
|<span data-ttu-id="e251e-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e251e-227">String</span><span class="sxs-lookup"><span data-stu-id="e251e-227">String</span></span>|  
|<span data-ttu-id="e251e-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="e251e-229">String</span><span class="sxs-lookup"><span data-stu-id="e251e-229">String</span></span>|  
|<span data-ttu-id="e251e-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-230">PARAMETER_NAME</span></span>|<span data-ttu-id="e251e-231">String</span><span class="sxs-lookup"><span data-stu-id="e251e-231">String</span></span>|  
|<span data-ttu-id="e251e-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e251e-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="e251e-233">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-233">Int32</span></span>|  
|<span data-ttu-id="e251e-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="e251e-235">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-235">Int32</span></span>|  
|<span data-ttu-id="e251e-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e251e-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="e251e-237">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-237">Boolean</span></span>|  
|<span data-ttu-id="e251e-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e251e-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="e251e-239">String</span><span class="sxs-lookup"><span data-stu-id="e251e-239">String</span></span>|  
|<span data-ttu-id="e251e-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e251e-240">IS_NULLABLE</span></span>|<span data-ttu-id="e251e-241">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-241">Boolean</span></span>|  
|<span data-ttu-id="e251e-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-242">DATA_TYPE</span></span>|<span data-ttu-id="e251e-243">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-243">Int32</span></span>|  
|<span data-ttu-id="e251e-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e251e-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e251e-245">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-245">Int64</span></span>|  
|<span data-ttu-id="e251e-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e251e-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e251e-247">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-247">Int64</span></span>|  
|<span data-ttu-id="e251e-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e251e-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e251e-249">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-249">Int32</span></span>|  
|<span data-ttu-id="e251e-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e251e-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="e251e-251">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-251">Int16</span></span>|  
|<span data-ttu-id="e251e-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-252">DESCRIPTION</span></span>|<span data-ttu-id="e251e-253">String</span><span class="sxs-lookup"><span data-stu-id="e251e-253">String</span></span>|  
|<span data-ttu-id="e251e-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-254">TYPE_NAME</span></span>|<span data-ttu-id="e251e-255">String</span><span class="sxs-lookup"><span data-stu-id="e251e-255">String</span></span>|  
|<span data-ttu-id="e251e-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="e251e-257">String</span><span class="sxs-lookup"><span data-stu-id="e251e-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="e251e-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="e251e-258">Catalog</span></span>  
  
|<span data-ttu-id="e251e-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-259">ColumnName</span></span>|<span data-ttu-id="e251e-260">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-261">CATALOG_NAME</span></span>|<span data-ttu-id="e251e-262">String</span><span class="sxs-lookup"><span data-stu-id="e251e-262">String</span></span>|  
|<span data-ttu-id="e251e-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-263">DESCRIPTION</span></span>|<span data-ttu-id="e251e-264">String</span><span class="sxs-lookup"><span data-stu-id="e251e-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e251e-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="e251e-265">Indexes</span></span>  
  
|<span data-ttu-id="e251e-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-266">ColumnName</span></span>|<span data-ttu-id="e251e-267">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-268">TABLE_CATALOG</span></span>|<span data-ttu-id="e251e-269">String</span><span class="sxs-lookup"><span data-stu-id="e251e-269">String</span></span>|  
|<span data-ttu-id="e251e-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="e251e-271">String</span><span class="sxs-lookup"><span data-stu-id="e251e-271">String</span></span>|  
|<span data-ttu-id="e251e-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-272">TABLE_NAME</span></span>|<span data-ttu-id="e251e-273">String</span><span class="sxs-lookup"><span data-stu-id="e251e-273">String</span></span>|  
|<span data-ttu-id="e251e-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-274">INDEX_CATALOG</span></span>|<span data-ttu-id="e251e-275">String</span><span class="sxs-lookup"><span data-stu-id="e251e-275">String</span></span>|  
|<span data-ttu-id="e251e-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="e251e-277">String</span><span class="sxs-lookup"><span data-stu-id="e251e-277">String</span></span>|  
|<span data-ttu-id="e251e-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-278">INDEX_NAME</span></span>|<span data-ttu-id="e251e-279">String</span><span class="sxs-lookup"><span data-stu-id="e251e-279">String</span></span>|  
|<span data-ttu-id="e251e-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e251e-280">PRIMARY_KEY</span></span>|<span data-ttu-id="e251e-281">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-281">Boolean</span></span>|  
|<span data-ttu-id="e251e-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e251e-282">UNIQUE</span></span>|<span data-ttu-id="e251e-283">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-283">Boolean</span></span>|  
|<span data-ttu-id="e251e-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e251e-284">CLUSTERED</span></span>|<span data-ttu-id="e251e-285">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-285">Boolean</span></span>|  
|<span data-ttu-id="e251e-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-286">TYPE</span></span>|<span data-ttu-id="e251e-287">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-287">Int32</span></span>|  
|<span data-ttu-id="e251e-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e251e-288">FILL_FACTOR</span></span>|<span data-ttu-id="e251e-289">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-289">Int32</span></span>|  
|<span data-ttu-id="e251e-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e251e-290">INITIAL_SIZE</span></span>|<span data-ttu-id="e251e-291">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-291">Int32</span></span>|  
|<span data-ttu-id="e251e-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="e251e-292">NULLS</span></span>|<span data-ttu-id="e251e-293">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-293">Int32</span></span>|  
|<span data-ttu-id="e251e-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e251e-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e251e-295">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-295">Boolean</span></span>|  
|<span data-ttu-id="e251e-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e251e-296">AUTO_UPDATE</span></span>|<span data-ttu-id="e251e-297">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-297">Boolean</span></span>|  
|<span data-ttu-id="e251e-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e251e-298">NULL_COLLATION</span></span>|<span data-ttu-id="e251e-299">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-299">Int32</span></span>|  
|<span data-ttu-id="e251e-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e251e-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="e251e-301">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-301">Int64</span></span>|  
|<span data-ttu-id="e251e-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-302">COLUMN_NAME</span></span>|<span data-ttu-id="e251e-303">String</span><span class="sxs-lookup"><span data-stu-id="e251e-303">String</span></span>|  
|<span data-ttu-id="e251e-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-304">COLUMN_GUID</span></span>|<span data-ttu-id="e251e-305">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-305">Guid</span></span>|  
|<span data-ttu-id="e251e-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e251e-306">COLUMN_PROPID</span></span>|<span data-ttu-id="e251e-307">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-307">Int64</span></span>|  
|<span data-ttu-id="e251e-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e251e-308">COLLATION</span></span>|<span data-ttu-id="e251e-309">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-309">Int16</span></span>|  
|<span data-ttu-id="e251e-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e251e-310">CARDINALITY</span></span>|<span data-ttu-id="e251e-311">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="e251e-311">Decimal</span></span>|  
|<span data-ttu-id="e251e-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="e251e-312">PAGES</span></span>|<span data-ttu-id="e251e-313">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-313">Int32</span></span>|  
|<span data-ttu-id="e251e-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e251e-314">FILTER_CONDITION</span></span>|<span data-ttu-id="e251e-315">String</span><span class="sxs-lookup"><span data-stu-id="e251e-315">String</span></span>|  
|<span data-ttu-id="e251e-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e251e-316">INTEGRATED</span></span>|<span data-ttu-id="e251e-317">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="e251e-318">Microsoft Oracle OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="e251e-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="e251e-319">Microsoft Oracle OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e251e-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="e251e-320">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e251e-320">Tables</span></span>  
  
- <span data-ttu-id="e251e-321">列</span><span class="sxs-lookup"><span data-stu-id="e251e-321">Columns</span></span>  
  
- <span data-ttu-id="e251e-322">手順</span><span class="sxs-lookup"><span data-stu-id="e251e-322">Procedures</span></span>  
  
- <span data-ttu-id="e251e-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e251e-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="e251e-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e251e-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="e251e-325">Views</span><span class="sxs-lookup"><span data-stu-id="e251e-325">Views</span></span>  
  
- <span data-ttu-id="e251e-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="e251e-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e251e-327">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e251e-327">Tables</span></span>  
  
|<span data-ttu-id="e251e-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-328">ColumnName</span></span>|<span data-ttu-id="e251e-329">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-330">TABLE_CATALOG</span></span>|<span data-ttu-id="e251e-331">String</span><span class="sxs-lookup"><span data-stu-id="e251e-331">String</span></span>|  
|<span data-ttu-id="e251e-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="e251e-333">String</span><span class="sxs-lookup"><span data-stu-id="e251e-333">String</span></span>|  
|<span data-ttu-id="e251e-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-334">TABLE_NAME</span></span>|<span data-ttu-id="e251e-335">String</span><span class="sxs-lookup"><span data-stu-id="e251e-335">String</span></span>|  
|<span data-ttu-id="e251e-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-336">TABLE_TYPE</span></span>|<span data-ttu-id="e251e-337">String</span><span class="sxs-lookup"><span data-stu-id="e251e-337">String</span></span>|  
|<span data-ttu-id="e251e-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-338">TABLE_GUID</span></span>|<span data-ttu-id="e251e-339">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-339">Guid</span></span>|  
|<span data-ttu-id="e251e-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-340">DESCRIPTION</span></span>|<span data-ttu-id="e251e-341">String</span><span class="sxs-lookup"><span data-stu-id="e251e-341">String</span></span>|  
|<span data-ttu-id="e251e-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e251e-342">TABLE_PROPID</span></span>|<span data-ttu-id="e251e-343">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-343">Int64</span></span>|  
|<span data-ttu-id="e251e-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e251e-344">DATE_CREATED</span></span>|<span data-ttu-id="e251e-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-345">DateTime</span></span>|  
|<span data-ttu-id="e251e-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e251e-346">DATE_MODIFIED</span></span>|<span data-ttu-id="e251e-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e251e-348">列</span><span class="sxs-lookup"><span data-stu-id="e251e-348">Columns</span></span>  
  
|<span data-ttu-id="e251e-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-349">ColumnName</span></span>|<span data-ttu-id="e251e-350">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-351">TABLE_CATALOG</span></span>|<span data-ttu-id="e251e-352">String</span><span class="sxs-lookup"><span data-stu-id="e251e-352">String</span></span>|  
|<span data-ttu-id="e251e-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="e251e-354">String</span><span class="sxs-lookup"><span data-stu-id="e251e-354">String</span></span>|  
|<span data-ttu-id="e251e-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-355">TABLE_NAME</span></span>|<span data-ttu-id="e251e-356">String</span><span class="sxs-lookup"><span data-stu-id="e251e-356">String</span></span>|  
|<span data-ttu-id="e251e-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-357">COLUMN_NAME</span></span>|<span data-ttu-id="e251e-358">String</span><span class="sxs-lookup"><span data-stu-id="e251e-358">String</span></span>|  
|<span data-ttu-id="e251e-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-359">COLUMN_GUID</span></span>|<span data-ttu-id="e251e-360">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-360">Guid</span></span>|  
|<span data-ttu-id="e251e-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e251e-361">COLUMN_PROPID</span></span>|<span data-ttu-id="e251e-362">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-362">Int64</span></span>|  
|<span data-ttu-id="e251e-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e251e-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="e251e-364">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-364">Int64</span></span>|  
|<span data-ttu-id="e251e-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e251e-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e251e-366">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-366">Boolean</span></span>|  
|<span data-ttu-id="e251e-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e251e-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e251e-368">String</span><span class="sxs-lookup"><span data-stu-id="e251e-368">String</span></span>|  
|<span data-ttu-id="e251e-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e251e-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="e251e-370">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-370">Int64</span></span>|  
|<span data-ttu-id="e251e-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e251e-371">IS_NULLABLE</span></span>|<span data-ttu-id="e251e-372">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-372">Boolean</span></span>|  
|<span data-ttu-id="e251e-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-373">DATA_TYPE</span></span>|<span data-ttu-id="e251e-374">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-374">Int32</span></span>|  
|<span data-ttu-id="e251e-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-375">TYPE_GUID</span></span>|<span data-ttu-id="e251e-376">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-376">Guid</span></span>|  
|<span data-ttu-id="e251e-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e251e-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e251e-378">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-378">Int64</span></span>|  
|<span data-ttu-id="e251e-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e251e-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e251e-380">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-380">Int64</span></span>|  
|<span data-ttu-id="e251e-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e251e-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e251e-382">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-382">Int32</span></span>|  
|<span data-ttu-id="e251e-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e251e-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="e251e-384">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-384">Int16</span></span>|  
|<span data-ttu-id="e251e-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e251e-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="e251e-386">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-386">Int64</span></span>|  
|<span data-ttu-id="e251e-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e251e-388">String</span><span class="sxs-lookup"><span data-stu-id="e251e-388">String</span></span>|  
|<span data-ttu-id="e251e-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e251e-390">String</span><span class="sxs-lookup"><span data-stu-id="e251e-390">String</span></span>|  
|<span data-ttu-id="e251e-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e251e-392">String</span><span class="sxs-lookup"><span data-stu-id="e251e-392">String</span></span>|  
|<span data-ttu-id="e251e-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="e251e-394">String</span><span class="sxs-lookup"><span data-stu-id="e251e-394">String</span></span>|  
|<span data-ttu-id="e251e-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e251e-396">String</span><span class="sxs-lookup"><span data-stu-id="e251e-396">String</span></span>|  
|<span data-ttu-id="e251e-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-397">COLLATION_NAME</span></span>|<span data-ttu-id="e251e-398">String</span><span class="sxs-lookup"><span data-stu-id="e251e-398">String</span></span>|  
|<span data-ttu-id="e251e-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e251e-400">String</span><span class="sxs-lookup"><span data-stu-id="e251e-400">String</span></span>|  
|<span data-ttu-id="e251e-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e251e-402">String</span><span class="sxs-lookup"><span data-stu-id="e251e-402">String</span></span>|  
|<span data-ttu-id="e251e-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-403">DOMAIN_NAME</span></span>|<span data-ttu-id="e251e-404">String</span><span class="sxs-lookup"><span data-stu-id="e251e-404">String</span></span>|  
|<span data-ttu-id="e251e-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-405">DESCRIPTION</span></span>|<span data-ttu-id="e251e-406">String</span><span class="sxs-lookup"><span data-stu-id="e251e-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e251e-407">手順</span><span class="sxs-lookup"><span data-stu-id="e251e-407">Procedures</span></span>  
  
|<span data-ttu-id="e251e-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-408">ColumnName</span></span>|<span data-ttu-id="e251e-409">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e251e-411">String</span><span class="sxs-lookup"><span data-stu-id="e251e-411">String</span></span>|  
|<span data-ttu-id="e251e-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e251e-413">String</span><span class="sxs-lookup"><span data-stu-id="e251e-413">String</span></span>|  
|<span data-ttu-id="e251e-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="e251e-415">String</span><span class="sxs-lookup"><span data-stu-id="e251e-415">String</span></span>|  
|<span data-ttu-id="e251e-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e251e-417">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-417">Int16</span></span>|  
|<span data-ttu-id="e251e-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e251e-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e251e-419">String</span><span class="sxs-lookup"><span data-stu-id="e251e-419">String</span></span>|  
|<span data-ttu-id="e251e-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-420">DESCRIPTION</span></span>|<span data-ttu-id="e251e-421">String</span><span class="sxs-lookup"><span data-stu-id="e251e-421">String</span></span>|  
|<span data-ttu-id="e251e-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e251e-422">DATE_CREATED</span></span>|<span data-ttu-id="e251e-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-423">DateTime</span></span>|  
|<span data-ttu-id="e251e-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e251e-424">DATE_MODIFIED</span></span>|<span data-ttu-id="e251e-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e251e-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e251e-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e251e-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-427">ColumnName</span></span>|<span data-ttu-id="e251e-428">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e251e-430">String</span><span class="sxs-lookup"><span data-stu-id="e251e-430">String</span></span>|  
|<span data-ttu-id="e251e-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e251e-432">String</span><span class="sxs-lookup"><span data-stu-id="e251e-432">String</span></span>|  
|<span data-ttu-id="e251e-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="e251e-434">String</span><span class="sxs-lookup"><span data-stu-id="e251e-434">String</span></span>|  
|<span data-ttu-id="e251e-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-435">COLUMN_NAME</span></span>|<span data-ttu-id="e251e-436">String</span><span class="sxs-lookup"><span data-stu-id="e251e-436">String</span></span>|  
|<span data-ttu-id="e251e-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-437">COLUMN_GUID</span></span>|<span data-ttu-id="e251e-438">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-438">Guid</span></span>|  
|<span data-ttu-id="e251e-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e251e-439">COLUMN_PROPID</span></span>|<span data-ttu-id="e251e-440">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-440">Int64</span></span>|  
|<span data-ttu-id="e251e-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="e251e-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="e251e-442">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-442">Int64</span></span>|  
|<span data-ttu-id="e251e-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e251e-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="e251e-444">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-444">Int64</span></span>|  
|<span data-ttu-id="e251e-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e251e-445">IS_NULLABLE</span></span>|<span data-ttu-id="e251e-446">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-446">Boolean</span></span>|  
|<span data-ttu-id="e251e-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-447">DATA_TYPE</span></span>|<span data-ttu-id="e251e-448">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-448">Int32</span></span>|  
|<span data-ttu-id="e251e-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-449">TYPE_GUID</span></span>|<span data-ttu-id="e251e-450">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-450">Guid</span></span>|  
|<span data-ttu-id="e251e-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e251e-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e251e-452">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-452">Int64</span></span>|  
|<span data-ttu-id="e251e-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e251e-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e251e-454">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-454">Int64</span></span>|  
|<span data-ttu-id="e251e-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e251e-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e251e-456">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-456">Int32</span></span>|  
|<span data-ttu-id="e251e-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e251e-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="e251e-458">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-458">Int16</span></span>|  
|<span data-ttu-id="e251e-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-459">DESCRIPTION</span></span>|<span data-ttu-id="e251e-460">String</span><span class="sxs-lookup"><span data-stu-id="e251e-460">String</span></span>|  
|<span data-ttu-id="e251e-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e251e-461">OVERLOAD</span></span>|<span data-ttu-id="e251e-462">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="e251e-463">Views</span><span class="sxs-lookup"><span data-stu-id="e251e-463">Views</span></span>  
  
|<span data-ttu-id="e251e-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-464">ColumnName</span></span>|<span data-ttu-id="e251e-465">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-466">TABLE_CATALOG</span></span>|<span data-ttu-id="e251e-467">String</span><span class="sxs-lookup"><span data-stu-id="e251e-467">String</span></span>|  
|<span data-ttu-id="e251e-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="e251e-469">String</span><span class="sxs-lookup"><span data-stu-id="e251e-469">String</span></span>|  
|<span data-ttu-id="e251e-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-470">TABLE_NAME</span></span>|<span data-ttu-id="e251e-471">String</span><span class="sxs-lookup"><span data-stu-id="e251e-471">String</span></span>|  
|<span data-ttu-id="e251e-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e251e-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="e251e-473">String</span><span class="sxs-lookup"><span data-stu-id="e251e-473">String</span></span>|  
|<span data-ttu-id="e251e-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-474">CHECK_OPTION</span></span>|<span data-ttu-id="e251e-475">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-475">Boolean</span></span>|  
|<span data-ttu-id="e251e-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="e251e-476">IS_UPDATABLE</span></span>|<span data-ttu-id="e251e-477">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-477">Boolean</span></span>|  
|<span data-ttu-id="e251e-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-478">DESCRIPTION</span></span>|<span data-ttu-id="e251e-479">String</span><span class="sxs-lookup"><span data-stu-id="e251e-479">String</span></span>|  
|<span data-ttu-id="e251e-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e251e-480">DATE_CREATED</span></span>|<span data-ttu-id="e251e-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-481">DateTime</span></span>|  
|<span data-ttu-id="e251e-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e251e-482">DATE_MODIFIED</span></span>|<span data-ttu-id="e251e-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e251e-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="e251e-484">Indexes</span></span>  
  
|<span data-ttu-id="e251e-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-485">ColumnName</span></span>|<span data-ttu-id="e251e-486">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-487">TABLE_CATALOG</span></span>|<span data-ttu-id="e251e-488">String</span><span class="sxs-lookup"><span data-stu-id="e251e-488">String</span></span>|  
|<span data-ttu-id="e251e-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="e251e-490">String</span><span class="sxs-lookup"><span data-stu-id="e251e-490">String</span></span>|  
|<span data-ttu-id="e251e-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-491">TABLE_NAME</span></span>|<span data-ttu-id="e251e-492">String</span><span class="sxs-lookup"><span data-stu-id="e251e-492">String</span></span>|  
|<span data-ttu-id="e251e-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-493">INDEX_CATALOG</span></span>|<span data-ttu-id="e251e-494">String</span><span class="sxs-lookup"><span data-stu-id="e251e-494">String</span></span>|  
|<span data-ttu-id="e251e-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="e251e-496">String</span><span class="sxs-lookup"><span data-stu-id="e251e-496">String</span></span>|  
|<span data-ttu-id="e251e-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-497">INDEX_NAME</span></span>|<span data-ttu-id="e251e-498">String</span><span class="sxs-lookup"><span data-stu-id="e251e-498">String</span></span>|  
|<span data-ttu-id="e251e-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e251e-499">PRIMARY_KEY</span></span>|<span data-ttu-id="e251e-500">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-500">Boolean</span></span>|  
|<span data-ttu-id="e251e-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e251e-501">UNIQUE</span></span>|<span data-ttu-id="e251e-502">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-502">Boolean</span></span>|  
|<span data-ttu-id="e251e-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e251e-503">CLUSTERED</span></span>|<span data-ttu-id="e251e-504">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-504">Boolean</span></span>|  
|<span data-ttu-id="e251e-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-505">TYPE</span></span>|<span data-ttu-id="e251e-506">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-506">Int32</span></span>|  
|<span data-ttu-id="e251e-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e251e-507">FILL_FACTOR</span></span>|<span data-ttu-id="e251e-508">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-508">Int32</span></span>|  
|<span data-ttu-id="e251e-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e251e-509">INITIAL_SIZE</span></span>|<span data-ttu-id="e251e-510">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-510">Int32</span></span>|  
|<span data-ttu-id="e251e-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="e251e-511">NULLS</span></span>|<span data-ttu-id="e251e-512">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-512">Int32</span></span>|  
|<span data-ttu-id="e251e-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e251e-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e251e-514">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-514">Boolean</span></span>|  
|<span data-ttu-id="e251e-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e251e-515">AUTO_UPDATE</span></span>|<span data-ttu-id="e251e-516">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-516">Boolean</span></span>|  
|<span data-ttu-id="e251e-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e251e-517">NULL_COLLATION</span></span>|<span data-ttu-id="e251e-518">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-518">Int32</span></span>|  
|<span data-ttu-id="e251e-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e251e-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="e251e-520">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-520">Int64</span></span>|  
|<span data-ttu-id="e251e-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-521">COLUMN_NAME</span></span>|<span data-ttu-id="e251e-522">String</span><span class="sxs-lookup"><span data-stu-id="e251e-522">String</span></span>|  
|<span data-ttu-id="e251e-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-523">COLUMN_GUID</span></span>|<span data-ttu-id="e251e-524">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-524">Guid</span></span>|  
|<span data-ttu-id="e251e-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e251e-525">COLUMN_PROPID</span></span>|<span data-ttu-id="e251e-526">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-526">Int64</span></span>|  
|<span data-ttu-id="e251e-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e251e-527">COLLATION</span></span>|<span data-ttu-id="e251e-528">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-528">Int16</span></span>|  
|<span data-ttu-id="e251e-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e251e-529">CARDINALITY</span></span>|<span data-ttu-id="e251e-530">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="e251e-530">Decimal</span></span>|  
|<span data-ttu-id="e251e-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="e251e-531">PAGES</span></span>|<span data-ttu-id="e251e-532">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-532">Int32</span></span>|  
|<span data-ttu-id="e251e-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e251e-533">FILTER_CONDITION</span></span>|<span data-ttu-id="e251e-534">String</span><span class="sxs-lookup"><span data-stu-id="e251e-534">String</span></span>|  
|<span data-ttu-id="e251e-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e251e-535">INTEGRATED</span></span>|<span data-ttu-id="e251e-536">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="e251e-537">Microsoft Jet OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="e251e-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="e251e-538">Microsoft Jet OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e251e-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="e251e-539">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e251e-539">Tables</span></span>  
  
- <span data-ttu-id="e251e-540">列</span><span class="sxs-lookup"><span data-stu-id="e251e-540">Columns</span></span>  
  
- <span data-ttu-id="e251e-541">手順</span><span class="sxs-lookup"><span data-stu-id="e251e-541">Procedures</span></span>  
  
- <span data-ttu-id="e251e-542">Views</span><span class="sxs-lookup"><span data-stu-id="e251e-542">Views</span></span>  
  
- <span data-ttu-id="e251e-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="e251e-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e251e-544">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e251e-544">Tables</span></span>  
  
|<span data-ttu-id="e251e-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-545">ColumnName</span></span>|<span data-ttu-id="e251e-546">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-547">TABLE_CATALOG</span></span>|<span data-ttu-id="e251e-548">String</span><span class="sxs-lookup"><span data-stu-id="e251e-548">String</span></span>|  
|<span data-ttu-id="e251e-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="e251e-550">String</span><span class="sxs-lookup"><span data-stu-id="e251e-550">String</span></span>|  
|<span data-ttu-id="e251e-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-551">TABLE_NAME</span></span>|<span data-ttu-id="e251e-552">String</span><span class="sxs-lookup"><span data-stu-id="e251e-552">String</span></span>|  
|<span data-ttu-id="e251e-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-553">TABLE_TYPE</span></span>|<span data-ttu-id="e251e-554">String</span><span class="sxs-lookup"><span data-stu-id="e251e-554">String</span></span>|  
|<span data-ttu-id="e251e-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-555">TABLE_GUID</span></span>|<span data-ttu-id="e251e-556">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-556">Guid</span></span>|  
|<span data-ttu-id="e251e-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-557">DESCRIPTION</span></span>|<span data-ttu-id="e251e-558">String</span><span class="sxs-lookup"><span data-stu-id="e251e-558">String</span></span>|  
|<span data-ttu-id="e251e-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e251e-559">TABLE_PROPID</span></span>|<span data-ttu-id="e251e-560">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-560">Int64</span></span>|  
|<span data-ttu-id="e251e-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e251e-561">DATE_CREATED</span></span>|<span data-ttu-id="e251e-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-562">DateTime</span></span>|  
|<span data-ttu-id="e251e-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e251e-563">DATE_MODIFIED</span></span>|<span data-ttu-id="e251e-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e251e-565">列</span><span class="sxs-lookup"><span data-stu-id="e251e-565">Columns</span></span>  
  
|<span data-ttu-id="e251e-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-566">ColumnName</span></span>|<span data-ttu-id="e251e-567">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-568">TABLE_CATALOG</span></span>|<span data-ttu-id="e251e-569">String</span><span class="sxs-lookup"><span data-stu-id="e251e-569">String</span></span>|  
|<span data-ttu-id="e251e-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="e251e-571">String</span><span class="sxs-lookup"><span data-stu-id="e251e-571">String</span></span>|  
|<span data-ttu-id="e251e-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-572">TABLE_NAME</span></span>|<span data-ttu-id="e251e-573">String</span><span class="sxs-lookup"><span data-stu-id="e251e-573">String</span></span>|  
|<span data-ttu-id="e251e-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-574">COLUMN_NAME</span></span>|<span data-ttu-id="e251e-575">String</span><span class="sxs-lookup"><span data-stu-id="e251e-575">String</span></span>|  
|<span data-ttu-id="e251e-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-576">COLUMN_GUID</span></span>|<span data-ttu-id="e251e-577">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-577">Guid</span></span>|  
|<span data-ttu-id="e251e-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e251e-578">COLUMN_PROPID</span></span>|<span data-ttu-id="e251e-579">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-579">Int64</span></span>|  
|<span data-ttu-id="e251e-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e251e-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="e251e-581">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-581">Int64</span></span>|  
|<span data-ttu-id="e251e-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e251e-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e251e-583">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-583">Boolean</span></span>|  
|<span data-ttu-id="e251e-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e251e-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e251e-585">String</span><span class="sxs-lookup"><span data-stu-id="e251e-585">String</span></span>|  
|<span data-ttu-id="e251e-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e251e-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="e251e-587">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-587">Int64</span></span>|  
|<span data-ttu-id="e251e-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e251e-588">IS_NULLABLE</span></span>|<span data-ttu-id="e251e-589">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-589">Boolean</span></span>|  
|<span data-ttu-id="e251e-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-590">DATA_TYPE</span></span>|<span data-ttu-id="e251e-591">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-591">Int32</span></span>|  
|<span data-ttu-id="e251e-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-592">TYPE_GUID</span></span>|<span data-ttu-id="e251e-593">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-593">Guid</span></span>|  
|<span data-ttu-id="e251e-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e251e-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e251e-595">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-595">Int64</span></span>|  
|<span data-ttu-id="e251e-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e251e-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e251e-597">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-597">Int64</span></span>|  
|<span data-ttu-id="e251e-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e251e-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e251e-599">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-599">Int32</span></span>|  
|<span data-ttu-id="e251e-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e251e-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="e251e-601">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-601">Int16</span></span>|  
|<span data-ttu-id="e251e-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e251e-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="e251e-603">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-603">Int64</span></span>|  
|<span data-ttu-id="e251e-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e251e-605">String</span><span class="sxs-lookup"><span data-stu-id="e251e-605">String</span></span>|  
|<span data-ttu-id="e251e-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e251e-607">String</span><span class="sxs-lookup"><span data-stu-id="e251e-607">String</span></span>|  
|<span data-ttu-id="e251e-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e251e-609">String</span><span class="sxs-lookup"><span data-stu-id="e251e-609">String</span></span>|  
|<span data-ttu-id="e251e-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="e251e-611">String</span><span class="sxs-lookup"><span data-stu-id="e251e-611">String</span></span>|  
|<span data-ttu-id="e251e-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e251e-613">String</span><span class="sxs-lookup"><span data-stu-id="e251e-613">String</span></span>|  
|<span data-ttu-id="e251e-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-614">COLLATION_NAME</span></span>|<span data-ttu-id="e251e-615">String</span><span class="sxs-lookup"><span data-stu-id="e251e-615">String</span></span>|  
|<span data-ttu-id="e251e-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e251e-617">String</span><span class="sxs-lookup"><span data-stu-id="e251e-617">String</span></span>|  
|<span data-ttu-id="e251e-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e251e-619">String</span><span class="sxs-lookup"><span data-stu-id="e251e-619">String</span></span>|  
|<span data-ttu-id="e251e-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-620">DOMAIN_NAME</span></span>|<span data-ttu-id="e251e-621">String</span><span class="sxs-lookup"><span data-stu-id="e251e-621">String</span></span>|  
|<span data-ttu-id="e251e-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-622">DESCRIPTION</span></span>|<span data-ttu-id="e251e-623">String</span><span class="sxs-lookup"><span data-stu-id="e251e-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e251e-624">手順</span><span class="sxs-lookup"><span data-stu-id="e251e-624">Procedures</span></span>  
  
|<span data-ttu-id="e251e-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-625">ColumnName</span></span>|<span data-ttu-id="e251e-626">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e251e-628">String</span><span class="sxs-lookup"><span data-stu-id="e251e-628">String</span></span>|  
|<span data-ttu-id="e251e-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e251e-630">String</span><span class="sxs-lookup"><span data-stu-id="e251e-630">String</span></span>|  
|<span data-ttu-id="e251e-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="e251e-632">String</span><span class="sxs-lookup"><span data-stu-id="e251e-632">String</span></span>|  
|<span data-ttu-id="e251e-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e251e-634">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-634">Int16</span></span>|  
|<span data-ttu-id="e251e-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e251e-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e251e-636">String</span><span class="sxs-lookup"><span data-stu-id="e251e-636">String</span></span>|  
|<span data-ttu-id="e251e-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-637">DESCRIPTION</span></span>|<span data-ttu-id="e251e-638">String</span><span class="sxs-lookup"><span data-stu-id="e251e-638">String</span></span>|  
|<span data-ttu-id="e251e-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e251e-639">DATE_CREATED</span></span>|<span data-ttu-id="e251e-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-640">DateTime</span></span>|  
|<span data-ttu-id="e251e-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e251e-641">DATE_MODIFIED</span></span>|<span data-ttu-id="e251e-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="e251e-643">Views</span><span class="sxs-lookup"><span data-stu-id="e251e-643">Views</span></span>  
  
|<span data-ttu-id="e251e-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-644">ColumnName</span></span>|<span data-ttu-id="e251e-645">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-646">TABLE_CATALOG</span></span>|<span data-ttu-id="e251e-647">String</span><span class="sxs-lookup"><span data-stu-id="e251e-647">String</span></span>|  
|<span data-ttu-id="e251e-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="e251e-649">String</span><span class="sxs-lookup"><span data-stu-id="e251e-649">String</span></span>|  
|<span data-ttu-id="e251e-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-650">TABLE_NAME</span></span>|<span data-ttu-id="e251e-651">String</span><span class="sxs-lookup"><span data-stu-id="e251e-651">String</span></span>|  
|<span data-ttu-id="e251e-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e251e-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="e251e-653">String</span><span class="sxs-lookup"><span data-stu-id="e251e-653">String</span></span>|  
|<span data-ttu-id="e251e-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-654">CHECK_OPTION</span></span>|<span data-ttu-id="e251e-655">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-655">Boolean</span></span>|  
|<span data-ttu-id="e251e-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="e251e-656">IS_UPDATABLE</span></span>|<span data-ttu-id="e251e-657">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-657">Boolean</span></span>|  
|<span data-ttu-id="e251e-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e251e-658">DESCRIPTION</span></span>|<span data-ttu-id="e251e-659">String</span><span class="sxs-lookup"><span data-stu-id="e251e-659">String</span></span>|  
|<span data-ttu-id="e251e-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e251e-660">DATE_CREATED</span></span>|<span data-ttu-id="e251e-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-661">DateTime</span></span>|  
|<span data-ttu-id="e251e-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e251e-662">DATE_MODIFIED</span></span>|<span data-ttu-id="e251e-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="e251e-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e251e-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="e251e-664">Indexes</span></span>  
  
|<span data-ttu-id="e251e-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e251e-665">ColumnName</span></span>|<span data-ttu-id="e251e-666">DataType</span><span class="sxs-lookup"><span data-stu-id="e251e-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e251e-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-667">TABLE_CATALOG</span></span>|<span data-ttu-id="e251e-668">String</span><span class="sxs-lookup"><span data-stu-id="e251e-668">String</span></span>|  
|<span data-ttu-id="e251e-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="e251e-670">String</span><span class="sxs-lookup"><span data-stu-id="e251e-670">String</span></span>|  
|<span data-ttu-id="e251e-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-671">TABLE_NAME</span></span>|<span data-ttu-id="e251e-672">String</span><span class="sxs-lookup"><span data-stu-id="e251e-672">String</span></span>|  
|<span data-ttu-id="e251e-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e251e-673">INDEX_CATALOG</span></span>|<span data-ttu-id="e251e-674">String</span><span class="sxs-lookup"><span data-stu-id="e251e-674">String</span></span>|  
|<span data-ttu-id="e251e-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e251e-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="e251e-676">String</span><span class="sxs-lookup"><span data-stu-id="e251e-676">String</span></span>|  
|<span data-ttu-id="e251e-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-677">INDEX_NAME</span></span>|<span data-ttu-id="e251e-678">String</span><span class="sxs-lookup"><span data-stu-id="e251e-678">String</span></span>|  
|<span data-ttu-id="e251e-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e251e-679">PRIMARY_KEY</span></span>|<span data-ttu-id="e251e-680">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-680">Boolean</span></span>|  
|<span data-ttu-id="e251e-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e251e-681">UNIQUE</span></span>|<span data-ttu-id="e251e-682">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-682">Boolean</span></span>|  
|<span data-ttu-id="e251e-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e251e-683">CLUSTERED</span></span>|<span data-ttu-id="e251e-684">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-684">Boolean</span></span>|  
|<span data-ttu-id="e251e-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="e251e-685">TYPE</span></span>|<span data-ttu-id="e251e-686">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-686">Int32</span></span>|  
|<span data-ttu-id="e251e-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e251e-687">FILL_FACTOR</span></span>|<span data-ttu-id="e251e-688">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-688">Int32</span></span>|  
|<span data-ttu-id="e251e-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e251e-689">INITIAL_SIZE</span></span>|<span data-ttu-id="e251e-690">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-690">Int32</span></span>|  
|<span data-ttu-id="e251e-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="e251e-691">NULLS</span></span>|<span data-ttu-id="e251e-692">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-692">Int32</span></span>|  
|<span data-ttu-id="e251e-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e251e-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e251e-694">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-694">Boolean</span></span>|  
|<span data-ttu-id="e251e-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e251e-695">AUTO_UPDATE</span></span>|<span data-ttu-id="e251e-696">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-696">Boolean</span></span>|  
|<span data-ttu-id="e251e-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e251e-697">NULL_COLLATION</span></span>|<span data-ttu-id="e251e-698">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-698">Int32</span></span>|  
|<span data-ttu-id="e251e-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e251e-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="e251e-700">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-700">Int64</span></span>|  
|<span data-ttu-id="e251e-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e251e-701">COLUMN_NAME</span></span>|<span data-ttu-id="e251e-702">String</span><span class="sxs-lookup"><span data-stu-id="e251e-702">String</span></span>|  
|<span data-ttu-id="e251e-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e251e-703">COLUMN_GUID</span></span>|<span data-ttu-id="e251e-704">Guid</span><span class="sxs-lookup"><span data-stu-id="e251e-704">Guid</span></span>|  
|<span data-ttu-id="e251e-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e251e-705">COLUMN_PROPID</span></span>|<span data-ttu-id="e251e-706">Int64</span><span class="sxs-lookup"><span data-stu-id="e251e-706">Int64</span></span>|  
|<span data-ttu-id="e251e-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e251e-707">COLLATION</span></span>|<span data-ttu-id="e251e-708">Int16</span><span class="sxs-lookup"><span data-stu-id="e251e-708">Int16</span></span>|  
|<span data-ttu-id="e251e-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e251e-709">CARDINALITY</span></span>|<span data-ttu-id="e251e-710">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="e251e-710">Decimal</span></span>|  
|<span data-ttu-id="e251e-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="e251e-711">PAGES</span></span>|<span data-ttu-id="e251e-712">Int32</span><span class="sxs-lookup"><span data-stu-id="e251e-712">Int32</span></span>|  
|<span data-ttu-id="e251e-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e251e-713">FILTER_CONDITION</span></span>|<span data-ttu-id="e251e-714">String</span><span class="sxs-lookup"><span data-stu-id="e251e-714">String</span></span>|  
|<span data-ttu-id="e251e-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e251e-715">INTEGRATED</span></span>|<span data-ttu-id="e251e-716">ブール型</span><span class="sxs-lookup"><span data-stu-id="e251e-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e251e-717">関連項目</span><span class="sxs-lookup"><span data-stu-id="e251e-717">See also</span></span>

- [<span data-ttu-id="e251e-718">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="e251e-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
