---
title: ODBC スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: f0240e99d2420b0956d3c144f837b39e094bb78a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794719"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="57087-102">ODBC スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="57087-102">ODBC Schema Collections</span></span>

<span data-ttu-id="57087-103">ここでは、Microsoft SQL Server、Oracle、および Microsoft Jet 用の各 ODBC ドライバーでのスキーマ コレクションのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="57087-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="57087-104">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="57087-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="57087-105">Microsoft SQL Server ODBC ドライバーは、共通のスキーマコレクションに加えて次のスキーマコレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="57087-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="57087-106">テーブル</span><span class="sxs-lookup"><span data-stu-id="57087-106">Tables</span></span>

- <span data-ttu-id="57087-107">インデックス</span><span class="sxs-lookup"><span data-stu-id="57087-107">Indexes</span></span>

- <span data-ttu-id="57087-108">[列]</span><span class="sxs-lookup"><span data-stu-id="57087-108">Columns</span></span>

- <span data-ttu-id="57087-109">手順</span><span class="sxs-lookup"><span data-stu-id="57087-109">Procedures</span></span>

- <span data-ttu-id="57087-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="57087-110">ProcedureColumns</span></span>

- <span data-ttu-id="57087-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="57087-111">ProcedureParameters</span></span>

- <span data-ttu-id="57087-112">Views</span><span class="sxs-lookup"><span data-stu-id="57087-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="57087-113">[テーブルとビュー]</span><span class="sxs-lookup"><span data-stu-id="57087-113">Tables and Views</span></span>

|<span data-ttu-id="57087-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-114">ColumnName</span></span>|<span data-ttu-id="57087-115">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="57087-116">TABLE_CAT</span></span>|<span data-ttu-id="57087-117">String</span><span class="sxs-lookup"><span data-stu-id="57087-117">String</span></span>|
|<span data-ttu-id="57087-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="57087-118">TABLE_SCHEM</span></span>|<span data-ttu-id="57087-119">String</span><span class="sxs-lookup"><span data-stu-id="57087-119">String</span></span>|
|<span data-ttu-id="57087-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-120">TABLE_NAME</span></span>|<span data-ttu-id="57087-121">String</span><span class="sxs-lookup"><span data-stu-id="57087-121">String</span></span>|
|<span data-ttu-id="57087-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-122">TABLE_TYPE</span></span>|<span data-ttu-id="57087-123">String</span><span class="sxs-lookup"><span data-stu-id="57087-123">String</span></span>|
|<span data-ttu-id="57087-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-124">REMARKS</span></span>|<span data-ttu-id="57087-125">String</span><span class="sxs-lookup"><span data-stu-id="57087-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="57087-126">インデックス</span><span class="sxs-lookup"><span data-stu-id="57087-126">Indexes</span></span>

|<span data-ttu-id="57087-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-127">ColumnName</span></span>|<span data-ttu-id="57087-128">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="57087-129">TABLE_CAT</span></span>|<span data-ttu-id="57087-130">String</span><span class="sxs-lookup"><span data-stu-id="57087-130">String</span></span>|
|<span data-ttu-id="57087-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="57087-131">TABLE_SCHEM</span></span>|<span data-ttu-id="57087-132">String</span><span class="sxs-lookup"><span data-stu-id="57087-132">String</span></span>|
|<span data-ttu-id="57087-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-133">TABLE_NAME</span></span>|<span data-ttu-id="57087-134">String</span><span class="sxs-lookup"><span data-stu-id="57087-134">String</span></span>|
|<span data-ttu-id="57087-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="57087-135">NON_UNIQUE</span></span>|<span data-ttu-id="57087-136">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-136">Int16</span></span>|
|<span data-ttu-id="57087-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="57087-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="57087-138">String</span><span class="sxs-lookup"><span data-stu-id="57087-138">String</span></span>|
|<span data-ttu-id="57087-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-139">INDEX_NAME</span></span>|<span data-ttu-id="57087-140">String</span><span class="sxs-lookup"><span data-stu-id="57087-140">String</span></span>|
|<span data-ttu-id="57087-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-141">TYPE</span></span>|<span data-ttu-id="57087-142">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-142">Int16</span></span>|
|<span data-ttu-id="57087-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="57087-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="57087-144">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-144">Int16</span></span>|
|<span data-ttu-id="57087-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-145">COLUMN_NAME</span></span>|<span data-ttu-id="57087-146">String</span><span class="sxs-lookup"><span data-stu-id="57087-146">String</span></span>|
|<span data-ttu-id="57087-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="57087-147">ASC_OR_DESC</span></span>|<span data-ttu-id="57087-148">String</span><span class="sxs-lookup"><span data-stu-id="57087-148">String</span></span>|
|<span data-ttu-id="57087-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="57087-149">CARDINALITY</span></span>|<span data-ttu-id="57087-150">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-150">Int32</span></span>|
|<span data-ttu-id="57087-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="57087-151">PAGES</span></span>|<span data-ttu-id="57087-152">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-152">Int32</span></span>|
|<span data-ttu-id="57087-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="57087-153">FILTER_CONDITION</span></span>|<span data-ttu-id="57087-154">String</span><span class="sxs-lookup"><span data-stu-id="57087-154">String</span></span>|
|<span data-ttu-id="57087-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="57087-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="57087-156">String</span><span class="sxs-lookup"><span data-stu-id="57087-156">String</span></span>|
|<span data-ttu-id="57087-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="57087-158">Byte</span><span class="sxs-lookup"><span data-stu-id="57087-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="57087-159">[列]</span><span class="sxs-lookup"><span data-stu-id="57087-159">Columns</span></span>

|<span data-ttu-id="57087-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-160">ColumnName</span></span>|<span data-ttu-id="57087-161">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="57087-162">TABLE_CAT</span></span>|<span data-ttu-id="57087-163">String</span><span class="sxs-lookup"><span data-stu-id="57087-163">String</span></span>|
|<span data-ttu-id="57087-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="57087-164">TABLE_SCHEM</span></span>|<span data-ttu-id="57087-165">String</span><span class="sxs-lookup"><span data-stu-id="57087-165">String</span></span>|
|<span data-ttu-id="57087-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-166">TABLE_NAME</span></span>|<span data-ttu-id="57087-167">String</span><span class="sxs-lookup"><span data-stu-id="57087-167">String</span></span>|
|<span data-ttu-id="57087-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-168">COLUMN_NAME</span></span>|<span data-ttu-id="57087-169">String</span><span class="sxs-lookup"><span data-stu-id="57087-169">String</span></span>|
|<span data-ttu-id="57087-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-170">DATA_TYPE</span></span>|<span data-ttu-id="57087-171">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-171">Int16</span></span>|
|<span data-ttu-id="57087-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-172">TYPE_NAME</span></span>|<span data-ttu-id="57087-173">String</span><span class="sxs-lookup"><span data-stu-id="57087-173">String</span></span>|
|<span data-ttu-id="57087-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="57087-174">COLUMN_SIZE</span></span>|<span data-ttu-id="57087-175">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-175">Int32</span></span>|
|<span data-ttu-id="57087-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="57087-177">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-177">Int32</span></span>|
|<span data-ttu-id="57087-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="57087-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="57087-179">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-179">Int16</span></span>|
|<span data-ttu-id="57087-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="57087-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="57087-181">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-181">Int16</span></span>|
|<span data-ttu-id="57087-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-182">NULLABLE</span></span>|<span data-ttu-id="57087-183">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-183">Int16</span></span>|
|<span data-ttu-id="57087-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-184">REMARKS</span></span>|<span data-ttu-id="57087-185">String</span><span class="sxs-lookup"><span data-stu-id="57087-185">String</span></span>|
|<span data-ttu-id="57087-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="57087-186">COLUMN_DEF</span></span>|<span data-ttu-id="57087-187">String</span><span class="sxs-lookup"><span data-stu-id="57087-187">String</span></span>|
|<span data-ttu-id="57087-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="57087-189">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-189">Int16</span></span>|
|<span data-ttu-id="57087-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="57087-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="57087-191">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-191">Int16</span></span>|
|<span data-ttu-id="57087-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="57087-193">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-193">Int32</span></span>|
|<span data-ttu-id="57087-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="57087-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="57087-195">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-195">Int32</span></span>|
|<span data-ttu-id="57087-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-196">IS_NULLABLE</span></span>|<span data-ttu-id="57087-197">String</span><span class="sxs-lookup"><span data-stu-id="57087-197">String</span></span>|
|<span data-ttu-id="57087-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="57087-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="57087-199">String</span><span class="sxs-lookup"><span data-stu-id="57087-199">String</span></span>|
|<span data-ttu-id="57087-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="57087-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="57087-201">String</span><span class="sxs-lookup"><span data-stu-id="57087-201">String</span></span>|
|<span data-ttu-id="57087-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="57087-203">Byte</span><span class="sxs-lookup"><span data-stu-id="57087-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="57087-204">手順</span><span class="sxs-lookup"><span data-stu-id="57087-204">Procedures</span></span>

|<span data-ttu-id="57087-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-205">ColumnName</span></span>|<span data-ttu-id="57087-206">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="57087-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="57087-208">String</span><span class="sxs-lookup"><span data-stu-id="57087-208">String</span></span>|
|<span data-ttu-id="57087-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="57087-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="57087-210">String</span><span class="sxs-lookup"><span data-stu-id="57087-210">String</span></span>|
|<span data-ttu-id="57087-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="57087-212">String</span><span class="sxs-lookup"><span data-stu-id="57087-212">String</span></span>|
|<span data-ttu-id="57087-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="57087-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="57087-214">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-214">Int32</span></span>|
|<span data-ttu-id="57087-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="57087-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="57087-216">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-216">Int32</span></span>|
|<span data-ttu-id="57087-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="57087-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="57087-218">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-218">Int32</span></span>|
|<span data-ttu-id="57087-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-219">REMARKS</span></span>|<span data-ttu-id="57087-220">String</span><span class="sxs-lookup"><span data-stu-id="57087-220">String</span></span>|
|<span data-ttu-id="57087-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="57087-222">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="57087-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="57087-223">ProcedureColumns</span></span>

|<span data-ttu-id="57087-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-224">ColumnName</span></span>|<span data-ttu-id="57087-225">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="57087-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="57087-227">String</span><span class="sxs-lookup"><span data-stu-id="57087-227">String</span></span>|
|<span data-ttu-id="57087-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="57087-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="57087-229">String</span><span class="sxs-lookup"><span data-stu-id="57087-229">String</span></span>|
|<span data-ttu-id="57087-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="57087-231">String</span><span class="sxs-lookup"><span data-stu-id="57087-231">String</span></span>|
|<span data-ttu-id="57087-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-232">COLUMN_NAME</span></span>|<span data-ttu-id="57087-233">String</span><span class="sxs-lookup"><span data-stu-id="57087-233">String</span></span>|
|<span data-ttu-id="57087-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-234">COLUMN_TYPE</span></span>|<span data-ttu-id="57087-235">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-235">Int16</span></span>|
|<span data-ttu-id="57087-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-236">DATA_TYPE</span></span>|<span data-ttu-id="57087-237">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-237">Int16</span></span>|
|<span data-ttu-id="57087-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-238">TYPE_NAME</span></span>|<span data-ttu-id="57087-239">String</span><span class="sxs-lookup"><span data-stu-id="57087-239">String</span></span>|
|<span data-ttu-id="57087-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="57087-240">COLUMN_SIZE</span></span>|<span data-ttu-id="57087-241">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-241">Int32</span></span>|
|<span data-ttu-id="57087-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="57087-243">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-243">Int32</span></span>|
|<span data-ttu-id="57087-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="57087-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="57087-245">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-245">Int16</span></span>|
|<span data-ttu-id="57087-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="57087-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="57087-247">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-247">Int16</span></span>|
|<span data-ttu-id="57087-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-248">NULLABLE</span></span>|<span data-ttu-id="57087-249">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-249">Int16</span></span>|
|<span data-ttu-id="57087-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-250">REMARKS</span></span>|<span data-ttu-id="57087-251">String</span><span class="sxs-lookup"><span data-stu-id="57087-251">String</span></span>|
|<span data-ttu-id="57087-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="57087-252">COLUMN_DEF</span></span>|<span data-ttu-id="57087-253">String</span><span class="sxs-lookup"><span data-stu-id="57087-253">String</span></span>|
|<span data-ttu-id="57087-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="57087-255">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-255">Int16</span></span>|
|<span data-ttu-id="57087-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="57087-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="57087-257">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-257">Int16</span></span>|
|<span data-ttu-id="57087-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="57087-259">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-259">Int32</span></span>|
|<span data-ttu-id="57087-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="57087-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="57087-261">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-261">Int32</span></span>|
|<span data-ttu-id="57087-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-262">IS_NULLABLE</span></span>|<span data-ttu-id="57087-263">String</span><span class="sxs-lookup"><span data-stu-id="57087-263">String</span></span>|
|<span data-ttu-id="57087-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="57087-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="57087-265">String</span><span class="sxs-lookup"><span data-stu-id="57087-265">String</span></span>|
|<span data-ttu-id="57087-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="57087-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="57087-267">String</span><span class="sxs-lookup"><span data-stu-id="57087-267">String</span></span>|
|<span data-ttu-id="57087-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="57087-269">Byte</span><span class="sxs-lookup"><span data-stu-id="57087-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="57087-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="57087-270">ProcedureParameters</span></span>

|<span data-ttu-id="57087-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-271">ColumnName</span></span>|<span data-ttu-id="57087-272">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="57087-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="57087-274">String</span><span class="sxs-lookup"><span data-stu-id="57087-274">String</span></span>|
|<span data-ttu-id="57087-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="57087-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="57087-276">String</span><span class="sxs-lookup"><span data-stu-id="57087-276">String</span></span>|
|<span data-ttu-id="57087-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="57087-278">String</span><span class="sxs-lookup"><span data-stu-id="57087-278">String</span></span>|
|<span data-ttu-id="57087-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-279">COLUMN_NAME</span></span>|<span data-ttu-id="57087-280">String</span><span class="sxs-lookup"><span data-stu-id="57087-280">String</span></span>|
|<span data-ttu-id="57087-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-281">COLUMN_TYPE</span></span>|<span data-ttu-id="57087-282">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-282">Int16</span></span>|
|<span data-ttu-id="57087-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-283">DATA_TYPE</span></span>|<span data-ttu-id="57087-284">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-284">Int16</span></span>|
|<span data-ttu-id="57087-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-285">TYPE_NAME</span></span>|<span data-ttu-id="57087-286">String</span><span class="sxs-lookup"><span data-stu-id="57087-286">String</span></span>|
|<span data-ttu-id="57087-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="57087-287">COLUMN_SIZE</span></span>|<span data-ttu-id="57087-288">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-288">Int32</span></span>|
|<span data-ttu-id="57087-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="57087-290">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-290">Int32</span></span>|
|<span data-ttu-id="57087-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="57087-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="57087-292">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-292">Int16</span></span>|
|<span data-ttu-id="57087-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="57087-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="57087-294">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-294">Int16</span></span>|
|<span data-ttu-id="57087-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-295">NULLABLE</span></span>|<span data-ttu-id="57087-296">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-296">Int16</span></span>|
|<span data-ttu-id="57087-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-297">REMARKS</span></span>|<span data-ttu-id="57087-298">String</span><span class="sxs-lookup"><span data-stu-id="57087-298">String</span></span>|
|<span data-ttu-id="57087-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="57087-299">COLUMN_DEF</span></span>|<span data-ttu-id="57087-300">String</span><span class="sxs-lookup"><span data-stu-id="57087-300">String</span></span>|
|<span data-ttu-id="57087-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="57087-302">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-302">Int16</span></span>|
|<span data-ttu-id="57087-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="57087-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="57087-304">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-304">Int16</span></span>|
|<span data-ttu-id="57087-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="57087-306">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-306">Int32</span></span>|
|<span data-ttu-id="57087-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="57087-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="57087-308">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-308">Int32</span></span>|
|<span data-ttu-id="57087-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-309">IS_NULLABLE</span></span>|<span data-ttu-id="57087-310">String</span><span class="sxs-lookup"><span data-stu-id="57087-310">String</span></span>|
|<span data-ttu-id="57087-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="57087-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="57087-312">String</span><span class="sxs-lookup"><span data-stu-id="57087-312">String</span></span>|
|<span data-ttu-id="57087-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="57087-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="57087-314">String</span><span class="sxs-lookup"><span data-stu-id="57087-314">String</span></span>|
|<span data-ttu-id="57087-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="57087-316">Byte</span><span class="sxs-lookup"><span data-stu-id="57087-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="57087-317">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="57087-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="57087-318">Microsoft SQL Server Oracle ODBC ドライバーは、共通のスキーマコレクションに加えて次のスキーマコレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="57087-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="57087-319">テーブル</span><span class="sxs-lookup"><span data-stu-id="57087-319">Tables</span></span>

- <span data-ttu-id="57087-320">[列]</span><span class="sxs-lookup"><span data-stu-id="57087-320">Columns</span></span>

- <span data-ttu-id="57087-321">手順</span><span class="sxs-lookup"><span data-stu-id="57087-321">Procedures</span></span>

- <span data-ttu-id="57087-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="57087-322">ProcedureColumns</span></span>

- <span data-ttu-id="57087-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="57087-323">ProcedureParameters</span></span>

- <span data-ttu-id="57087-324">Views</span><span class="sxs-lookup"><span data-stu-id="57087-324">Views</span></span>

- <span data-ttu-id="57087-325">インデックス</span><span class="sxs-lookup"><span data-stu-id="57087-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="57087-326">[テーブルとビュー]</span><span class="sxs-lookup"><span data-stu-id="57087-326">Tables and Views</span></span>

|<span data-ttu-id="57087-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-327">ColumnName</span></span>|<span data-ttu-id="57087-328">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="57087-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="57087-330">String</span><span class="sxs-lookup"><span data-stu-id="57087-330">String</span></span>|
|<span data-ttu-id="57087-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="57087-331">TABLE_OWNER</span></span>|<span data-ttu-id="57087-332">String</span><span class="sxs-lookup"><span data-stu-id="57087-332">String</span></span>|
|<span data-ttu-id="57087-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-333">TABLE_NAME</span></span>|<span data-ttu-id="57087-334">String</span><span class="sxs-lookup"><span data-stu-id="57087-334">String</span></span>|
|<span data-ttu-id="57087-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-335">TABLE_TYPE</span></span>|<span data-ttu-id="57087-336">String</span><span class="sxs-lookup"><span data-stu-id="57087-336">String</span></span>|
|<span data-ttu-id="57087-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-337">REMARKS</span></span>|<span data-ttu-id="57087-338">String</span><span class="sxs-lookup"><span data-stu-id="57087-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="57087-339">[列]</span><span class="sxs-lookup"><span data-stu-id="57087-339">Columns</span></span>

|<span data-ttu-id="57087-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-340">ColumnName</span></span>|<span data-ttu-id="57087-341">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="57087-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="57087-343">String</span><span class="sxs-lookup"><span data-stu-id="57087-343">String</span></span>|
|<span data-ttu-id="57087-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="57087-344">TABLE_OWNER</span></span>|<span data-ttu-id="57087-345">String</span><span class="sxs-lookup"><span data-stu-id="57087-345">String</span></span>|
|<span data-ttu-id="57087-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-346">TABLE_NAME</span></span>|<span data-ttu-id="57087-347">String</span><span class="sxs-lookup"><span data-stu-id="57087-347">String</span></span>|
|<span data-ttu-id="57087-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-348">COLUMN_NAME</span></span>|<span data-ttu-id="57087-349">String</span><span class="sxs-lookup"><span data-stu-id="57087-349">String</span></span>|
|<span data-ttu-id="57087-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-350">DATA_TYPE</span></span>|<span data-ttu-id="57087-351">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-351">Int16</span></span>|
|<span data-ttu-id="57087-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-352">TYPE_NAME</span></span>|<span data-ttu-id="57087-353">String</span><span class="sxs-lookup"><span data-stu-id="57087-353">String</span></span>|
|<span data-ttu-id="57087-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="57087-354">PRECISION</span></span>|<span data-ttu-id="57087-355">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-355">Int32</span></span>|
|<span data-ttu-id="57087-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-356">LENGTH</span></span>|<span data-ttu-id="57087-357">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-357">Int32</span></span>|
|<span data-ttu-id="57087-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="57087-358">SCALE</span></span>|<span data-ttu-id="57087-359">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-359">Int16</span></span>|
|<span data-ttu-id="57087-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="57087-360">RADIX</span></span>|<span data-ttu-id="57087-361">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-361">Int16</span></span>|
|<span data-ttu-id="57087-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-362">NULLABLE</span></span>|<span data-ttu-id="57087-363">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-363">Int16</span></span>|
|<span data-ttu-id="57087-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-364">REMARKS</span></span>|<span data-ttu-id="57087-365">String</span><span class="sxs-lookup"><span data-stu-id="57087-365">String</span></span>|
|<span data-ttu-id="57087-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="57087-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="57087-367">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="57087-368">手順</span><span class="sxs-lookup"><span data-stu-id="57087-368">Procedures</span></span>

|<span data-ttu-id="57087-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-369">ColumnName</span></span>|<span data-ttu-id="57087-370">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="57087-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="57087-372">String</span><span class="sxs-lookup"><span data-stu-id="57087-372">String</span></span>|
|<span data-ttu-id="57087-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="57087-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="57087-374">String</span><span class="sxs-lookup"><span data-stu-id="57087-374">String</span></span>|
|<span data-ttu-id="57087-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="57087-376">String</span><span class="sxs-lookup"><span data-stu-id="57087-376">String</span></span>|
|<span data-ttu-id="57087-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="57087-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="57087-378">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-378">Int16</span></span>|
|<span data-ttu-id="57087-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="57087-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="57087-380">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-380">Int16</span></span>|
|<span data-ttu-id="57087-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="57087-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="57087-382">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-382">Int16</span></span>|
|<span data-ttu-id="57087-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-383">REMARKS</span></span>|<span data-ttu-id="57087-384">String</span><span class="sxs-lookup"><span data-stu-id="57087-384">String</span></span>|
|<span data-ttu-id="57087-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="57087-386">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="57087-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="57087-387">ProcedureColumns</span></span>

|<span data-ttu-id="57087-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-388">ColumnName</span></span>|<span data-ttu-id="57087-389">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="57087-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="57087-391">String</span><span class="sxs-lookup"><span data-stu-id="57087-391">String</span></span>|
|<span data-ttu-id="57087-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="57087-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="57087-393">String</span><span class="sxs-lookup"><span data-stu-id="57087-393">String</span></span>|
|<span data-ttu-id="57087-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="57087-395">String</span><span class="sxs-lookup"><span data-stu-id="57087-395">String</span></span>|
|<span data-ttu-id="57087-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-396">COLUMN_NAME</span></span>|<span data-ttu-id="57087-397">String</span><span class="sxs-lookup"><span data-stu-id="57087-397">String</span></span>|
|<span data-ttu-id="57087-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-398">COLUMN_TYPE</span></span>|<span data-ttu-id="57087-399">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-399">Int16</span></span>|
|<span data-ttu-id="57087-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-400">DATA_TYPE</span></span>|<span data-ttu-id="57087-401">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-401">Int16</span></span>|
|<span data-ttu-id="57087-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-402">TYPE_NAME</span></span>|<span data-ttu-id="57087-403">String</span><span class="sxs-lookup"><span data-stu-id="57087-403">String</span></span>|
|<span data-ttu-id="57087-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="57087-404">PRECISION</span></span>|<span data-ttu-id="57087-405">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-405">Int32</span></span>|
|<span data-ttu-id="57087-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-406">LENGTH</span></span>|<span data-ttu-id="57087-407">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-407">Int32</span></span>|
|<span data-ttu-id="57087-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="57087-408">SCALE</span></span>|<span data-ttu-id="57087-409">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-409">Int16</span></span>|
|<span data-ttu-id="57087-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="57087-410">RADIX</span></span>|<span data-ttu-id="57087-411">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-411">Int16</span></span>|
|<span data-ttu-id="57087-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-412">NULLABLE</span></span>|<span data-ttu-id="57087-413">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-413">Int16</span></span>|
|<span data-ttu-id="57087-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-414">REMARKS</span></span>|<span data-ttu-id="57087-415">String</span><span class="sxs-lookup"><span data-stu-id="57087-415">String</span></span>|
|<span data-ttu-id="57087-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="57087-416">OVERLOAD</span></span>|<span data-ttu-id="57087-417">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-417">Int32</span></span>|
|<span data-ttu-id="57087-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="57087-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="57087-419">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="57087-420">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="57087-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="57087-421">Microsoft Jet ODBC Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="57087-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="57087-422">テーブル</span><span class="sxs-lookup"><span data-stu-id="57087-422">Tables</span></span>

- <span data-ttu-id="57087-423">インデックス</span><span class="sxs-lookup"><span data-stu-id="57087-423">Indexes</span></span>

- <span data-ttu-id="57087-424">[列]</span><span class="sxs-lookup"><span data-stu-id="57087-424">Columns</span></span>

- <span data-ttu-id="57087-425">手順</span><span class="sxs-lookup"><span data-stu-id="57087-425">Procedures</span></span>

- <span data-ttu-id="57087-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="57087-426">ProcedureColumns</span></span>

- <span data-ttu-id="57087-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="57087-427">ProcedureParameters</span></span>

- <span data-ttu-id="57087-428">Views</span><span class="sxs-lookup"><span data-stu-id="57087-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="57087-429">[テーブルとビュー]</span><span class="sxs-lookup"><span data-stu-id="57087-429">Tables and Views</span></span>

|<span data-ttu-id="57087-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-430">ColumnName</span></span>|<span data-ttu-id="57087-431">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="57087-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="57087-433">String</span><span class="sxs-lookup"><span data-stu-id="57087-433">String</span></span>|
|<span data-ttu-id="57087-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="57087-434">TABLE_OWNER</span></span>|<span data-ttu-id="57087-435">String</span><span class="sxs-lookup"><span data-stu-id="57087-435">String</span></span>|
|<span data-ttu-id="57087-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-436">TABLE_NAME</span></span>|<span data-ttu-id="57087-437">String</span><span class="sxs-lookup"><span data-stu-id="57087-437">String</span></span>|
|<span data-ttu-id="57087-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-438">TABLE_TYPE</span></span>|<span data-ttu-id="57087-439">String</span><span class="sxs-lookup"><span data-stu-id="57087-439">String</span></span>|
|<span data-ttu-id="57087-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-440">REMARKS</span></span>|<span data-ttu-id="57087-441">String</span><span class="sxs-lookup"><span data-stu-id="57087-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="57087-442">[列]</span><span class="sxs-lookup"><span data-stu-id="57087-442">Columns</span></span>

|<span data-ttu-id="57087-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-443">ColumnName</span></span>|<span data-ttu-id="57087-444">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="57087-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="57087-446">String</span><span class="sxs-lookup"><span data-stu-id="57087-446">String</span></span>|
|<span data-ttu-id="57087-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="57087-447">TABLE_OWNER</span></span>|<span data-ttu-id="57087-448">String</span><span class="sxs-lookup"><span data-stu-id="57087-448">String</span></span>|
|<span data-ttu-id="57087-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-449">TABLE_NAME</span></span>|<span data-ttu-id="57087-450">String</span><span class="sxs-lookup"><span data-stu-id="57087-450">String</span></span>|
|<span data-ttu-id="57087-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-451">COLUMN_NAME</span></span>|<span data-ttu-id="57087-452">String</span><span class="sxs-lookup"><span data-stu-id="57087-452">String</span></span>|
|<span data-ttu-id="57087-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-453">DATA_TYPE</span></span>|<span data-ttu-id="57087-454">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-454">Int16</span></span>|
|<span data-ttu-id="57087-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-455">TYPE_NAME</span></span>|<span data-ttu-id="57087-456">String</span><span class="sxs-lookup"><span data-stu-id="57087-456">String</span></span>|
|<span data-ttu-id="57087-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="57087-457">PRECISION</span></span>|<span data-ttu-id="57087-458">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-458">Int32</span></span>|
|<span data-ttu-id="57087-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-459">LENGTH</span></span>|<span data-ttu-id="57087-460">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-460">Int32</span></span>|
|<span data-ttu-id="57087-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="57087-461">SCALE</span></span>|<span data-ttu-id="57087-462">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-462">Int16</span></span>|
|<span data-ttu-id="57087-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="57087-463">RADIX</span></span>|<span data-ttu-id="57087-464">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-464">Int16</span></span>|
|<span data-ttu-id="57087-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-465">NULLABLE</span></span>|<span data-ttu-id="57087-466">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-466">Int16</span></span>|
|<span data-ttu-id="57087-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-467">REMARKS</span></span>|<span data-ttu-id="57087-468">String</span><span class="sxs-lookup"><span data-stu-id="57087-468">String</span></span>|
|<span data-ttu-id="57087-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="57087-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="57087-470">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="57087-471">手順</span><span class="sxs-lookup"><span data-stu-id="57087-471">Procedures</span></span>

|<span data-ttu-id="57087-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-472">ColumnName</span></span>|<span data-ttu-id="57087-473">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="57087-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="57087-475">String</span><span class="sxs-lookup"><span data-stu-id="57087-475">String</span></span>|
|<span data-ttu-id="57087-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="57087-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="57087-477">String</span><span class="sxs-lookup"><span data-stu-id="57087-477">String</span></span>|
|<span data-ttu-id="57087-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="57087-479">String</span><span class="sxs-lookup"><span data-stu-id="57087-479">String</span></span>|
|<span data-ttu-id="57087-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="57087-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="57087-481">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-481">Int16</span></span>|
|<span data-ttu-id="57087-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="57087-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="57087-483">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-483">Int16</span></span>|
|<span data-ttu-id="57087-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="57087-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="57087-485">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-485">Int16</span></span>|
|<span data-ttu-id="57087-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-486">REMARKS</span></span>|<span data-ttu-id="57087-487">String</span><span class="sxs-lookup"><span data-stu-id="57087-487">String</span></span>|
|<span data-ttu-id="57087-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="57087-489">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="57087-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="57087-490">ProcedureColumns</span></span>

|<span data-ttu-id="57087-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-491">ColumnName</span></span>|<span data-ttu-id="57087-492">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="57087-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="57087-494">String</span><span class="sxs-lookup"><span data-stu-id="57087-494">String</span></span>|
|<span data-ttu-id="57087-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="57087-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="57087-496">String</span><span class="sxs-lookup"><span data-stu-id="57087-496">String</span></span>|
|<span data-ttu-id="57087-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="57087-498">String</span><span class="sxs-lookup"><span data-stu-id="57087-498">String</span></span>|
|<span data-ttu-id="57087-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-499">COLUMN_NAME</span></span>|<span data-ttu-id="57087-500">String</span><span class="sxs-lookup"><span data-stu-id="57087-500">String</span></span>|
|<span data-ttu-id="57087-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-501">COLUMN_TYPE</span></span>|<span data-ttu-id="57087-502">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-502">Int16</span></span>|
|<span data-ttu-id="57087-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-503">DATA_TYPE</span></span>|<span data-ttu-id="57087-504">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-504">Int16</span></span>|
|<span data-ttu-id="57087-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-505">TYPE_NAME</span></span>|<span data-ttu-id="57087-506">String</span><span class="sxs-lookup"><span data-stu-id="57087-506">String</span></span>|
|<span data-ttu-id="57087-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="57087-507">PRECISION</span></span>|<span data-ttu-id="57087-508">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-508">Int32</span></span>|
|<span data-ttu-id="57087-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-509">LENGTH</span></span>|<span data-ttu-id="57087-510">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-510">Int32</span></span>|
|<span data-ttu-id="57087-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="57087-511">SCALE</span></span>|<span data-ttu-id="57087-512">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-512">Int16</span></span>|
|<span data-ttu-id="57087-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="57087-513">RADIX</span></span>|<span data-ttu-id="57087-514">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-514">Int16</span></span>|
|<span data-ttu-id="57087-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-515">NULLABLE</span></span>|<span data-ttu-id="57087-516">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-516">Int16</span></span>|
|<span data-ttu-id="57087-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-517">REMARKS</span></span>|<span data-ttu-id="57087-518">String</span><span class="sxs-lookup"><span data-stu-id="57087-518">String</span></span>|
|<span data-ttu-id="57087-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="57087-519">OVERLOAD</span></span>|<span data-ttu-id="57087-520">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-520">Int32</span></span>|
|<span data-ttu-id="57087-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="57087-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="57087-522">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="57087-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="57087-523">ProcedureParameters</span></span>

|<span data-ttu-id="57087-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="57087-524">ColumnName</span></span>|<span data-ttu-id="57087-525">DataType</span><span class="sxs-lookup"><span data-stu-id="57087-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="57087-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="57087-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="57087-527">String</span><span class="sxs-lookup"><span data-stu-id="57087-527">String</span></span>|
|<span data-ttu-id="57087-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="57087-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="57087-529">String</span><span class="sxs-lookup"><span data-stu-id="57087-529">String</span></span>|
|<span data-ttu-id="57087-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="57087-531">String</span><span class="sxs-lookup"><span data-stu-id="57087-531">String</span></span>|
|<span data-ttu-id="57087-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-532">COLUMN_NAME</span></span>|<span data-ttu-id="57087-533">String</span><span class="sxs-lookup"><span data-stu-id="57087-533">String</span></span>|
|<span data-ttu-id="57087-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-534">COLUMN_TYPE</span></span>|<span data-ttu-id="57087-535">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-535">Int16</span></span>|
|<span data-ttu-id="57087-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-536">DATA_TYPE</span></span>|<span data-ttu-id="57087-537">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-537">Int16</span></span>|
|<span data-ttu-id="57087-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="57087-538">TYPE_NAME</span></span>|<span data-ttu-id="57087-539">String</span><span class="sxs-lookup"><span data-stu-id="57087-539">String</span></span>|
|<span data-ttu-id="57087-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="57087-540">COLUMN_SIZE</span></span>|<span data-ttu-id="57087-541">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-541">Int32</span></span>|
|<span data-ttu-id="57087-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="57087-543">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-543">Int32</span></span>|
|<span data-ttu-id="57087-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="57087-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="57087-545">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-545">Int16</span></span>|
|<span data-ttu-id="57087-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="57087-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="57087-547">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-547">Int16</span></span>|
|<span data-ttu-id="57087-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-548">NULLABLE</span></span>|<span data-ttu-id="57087-549">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-549">Int16</span></span>|
|<span data-ttu-id="57087-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="57087-550">REMARKS</span></span>|<span data-ttu-id="57087-551">String</span><span class="sxs-lookup"><span data-stu-id="57087-551">String</span></span>|
|<span data-ttu-id="57087-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="57087-552">COLUMN_DEF</span></span>|<span data-ttu-id="57087-553">String</span><span class="sxs-lookup"><span data-stu-id="57087-553">String</span></span>|
|<span data-ttu-id="57087-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="57087-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="57087-555">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-555">Int16</span></span>|
|<span data-ttu-id="57087-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="57087-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="57087-557">Int16</span><span class="sxs-lookup"><span data-stu-id="57087-557">Int16</span></span>|
|<span data-ttu-id="57087-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="57087-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="57087-559">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-559">Int32</span></span>|
|<span data-ttu-id="57087-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="57087-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="57087-561">Int32</span><span class="sxs-lookup"><span data-stu-id="57087-561">Int32</span></span>|
|<span data-ttu-id="57087-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="57087-562">IS_NULLABLE</span></span>|<span data-ttu-id="57087-563">String</span><span class="sxs-lookup"><span data-stu-id="57087-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="57087-564">関連項目</span><span class="sxs-lookup"><span data-stu-id="57087-564">See also</span></span>

- [<span data-ttu-id="57087-565">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="57087-565">ADO.NET Overview</span></span>](ado-net-overview.md)
